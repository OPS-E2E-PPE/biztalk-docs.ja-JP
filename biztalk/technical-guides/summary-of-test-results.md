---
title: テスト結果の概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d95fbaa6-0e07-4086-bea2-0577d39ae7cd
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2eebcdef457716cab9ad61415bf3fe46db301b55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302994"
---
# <a name="summary-of-test-results"></a>テスト結果の概要
このトピックでは、結果、テスト シナリオをまとめたものです。  
  
## <a name="summary-of-test-results"></a>テスト結果の概要  
 [BizTalk サーバー仮想化のパフォーマンスのテスト](../technical-guides/testing-biztalk-server-virtualization-performance.md)このガイドのセクションでは、使用するテスト アプリケーションと、さまざまな構成について説明します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]テスト アプリケーションの実行対象となる環境。 テストのパフォーマンスを比較する実行された、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  /  [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] HYPER-V 仮想マシンで実行されている環境のパフォーマンスを物理ハードウェア上で実行されている環境です。 主要業績評価指標 (Kpi) がテスト中に測定には、次が含まれています。  
  
1.  メッセージのスループットの測定、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。  
  
2.  同期要求を送信した Visual Studio テスト クライアントで要求-応答の待機時間が測定される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
3.  プロセッサ使用率と 1 秒あたりのバッチ要求で計測される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。  
  
4.  ネットワークのスループットがで計測される、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
5.  使用可能なメモリ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
### <a name="throughput-comparison-sample-results"></a>スループットの比較サンプルの結果  
 すべての他の要因が等しければのスループット、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションによって測定される、"BizTalk: メッセージング ドキュメント処理数/秒"の範囲が 67% から 94.3% の達成可能なスループットとパフォーマンス モニター カウンター両方、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]環境内のコンピューターは、物理ハードウェアにインストールされていた。  
  
 ときに、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]環境内のコンピューターは、HYPER-V 仮想マシンにインストールされていた、ソリューションのスループットが大幅に低下する確認されました、HYPER-V で必要な CPU オーバーヘッドを原因と考えられるこのスループットの低下します。  
  
### <a name="latency-comparison-sample-results"></a>待機時間の比較サンプルの結果  
 によって測定される、BizTalk Server ソリューションの待機時間、HYPER-V 仮想マシン上の BizTalk Server 環境で使用する BizTalk Server コンピューターが実行されたときに、等しい、されているその他のすべての要因と、"BizTalk: メッセージング遅延/要求-応答の遅延時間 (秒)"パフォーマンス モニター カウンターの範囲は 66.9% から 94.3% 達成可能な待機時間に、BizTalk Server 環境で使用する BizTalk Server コンピューターが物理ハードウェアにインストールされていたとします。  
  
 ときに、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]環境内のコンピューターは、HYPER-V 仮想マシンにインストールされていた、ソリューションのスループットが大幅に低下する計測された、このスループットの低下原因と考えられる、でHYPER-Vに必要なCPUのオーバーヘッド[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]仮想マシン。  
  
### <a name="sql-server-processor-utilization-and-batch-requests-per-second-sample-results"></a>SQL Server のプロセッサ使用率と 2 つ目のサンプル結果あたりのバッチ要求  
 SQL Server のプロセッサ使用率 \SQL\Processor(_Total) によって測定される\\% Processor Time カウンタが約 88% の低から 90.1% の high まで、すべてのテスト環境で同じです。 ありませんが、\SQL Server:SQL Statistics\Batch 間に大きな違い要求数/秒が統合された環境 (4520) で測定され、\SQL Server:SQL Statistics\Batch 要求数/秒が物理環境 (6350) で測定します。 \SQL Server:SQL Statistics\Batch 要求数/秒パフォーマンス モニター カウンターは、SQL Server によって実行される作業量を示す優れた指標を提供します。 バッチ要求数/秒を HYPER-V 環境で SQL Server が実行されている場合に削減は、HYPER-V で必要な CPU オーバーヘッドを属性付けすることができます。  
  
### <a name="biztalk-server-and-sql-server-network-throughput-sample-results"></a>BizTalk Server と SQL Server ネットワークのスループットのサンプルの結果  
 HYPER-V 仮想マシンで実行されている BizTalk Server のネットワーク スループットがから約 70 ~ 96%、特定のテスト環境に応じて、物理 BizTalk サーバーで達成されるネットワーク スループットの範囲内に確認されました。 HYPER-V 仮想マシンで実行されている SQL Server のネットワーク スループットがから約 68% から 81% の物理 SQL server の特定のテスト環境に応じて再び達成されるネットワーク スループットの範囲内に確認されました。 観察対象のネットワークのスループットのデルタは、HYPER-V ハイパーバイザーのリソース要件を属性付けすることができます。  
  
### <a name="biztalk-server-and-sql-server-available-memory-sample-results"></a>BizTalk Server と SQL Server の使用可能なメモリ サンプルの結果  
 SQL Server と BizTalk Server \Memory\Available Mbytes パフォーマンス モニター カウンターによって測定に使用できる合計メモリは、すべてのテスト シナリオ全体で一貫性でした。