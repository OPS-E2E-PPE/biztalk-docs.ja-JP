---
title: テスト結果の概要 |Microsoft Docs
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
ms.openlocfilehash: ad5550a073101e2a30555f90ad6bd879edff3a79
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997963"
---
# <a name="summary-of-test-results"></a>テスト結果の概要
このトピックでは、テスト シナリオの結果をまとめたものです。  
  
## <a name="summary-of-test-results"></a>テスト結果の概要  
 [BizTalk サーバー仮想化のパフォーマンスのテスト](../technical-guides/testing-biztalk-server-virtualization-performance.md)このガイドのセクションは、使用するテスト アプリケーションと、さまざまな構成について説明します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]テスト アプリケーションの実行対象となる環境。 パフォーマンスを比較するテストが実行された、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  /  [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]物理ハードウェア上で HYPER-V 仮想マシンで実行されている環境のパフォーマンスで実行される環境。 主要業績評価指標 (Kpi) がテスト中に測定には、次が含まれています。  
  
1. メッセージのスループットの測定、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。  
  
2. Visual Studio テスト クライアントを同期要求を送信した上で要求-応答の待機時間が計測されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
3. プロセッサ使用率と 1 秒あたりのバッチ要求で計測される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。  
  
4. ネットワークのスループットが計測される、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
5. 使用可能なメモリ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
### <a name="throughput-comparison-sample-results"></a>スループットの比較サンプルの結果  
 すべて他の要因が等しければのスループット、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションによって測定される、"BizTalk: メッセージング ドキュメント処理数/秒"パフォーマンス モニター カウンターが達成可能なスループットの 94.3% と 67% から範囲両方、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]環境内のコンピューターが物理ハードウェアにインストールされています。  
  
 ときに、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]環境内のコンピューターが HYPER-V 仮想マシンにインストールされた、ソリューションのスループットが大幅に低下する検出された、このスループットの低下は、HYPER-V に必要な CPU オーバーヘッドに原因があります。  
  
### <a name="latency-comparison-sample-results"></a>待機時間の比較サンプル結果  
 BizTalk Server 環境で使用する BizTalk Server コンピューターが HYPER-V 仮想マシンによって測定される、BizTalk Server ソリューションの待機時間で実行されたときに等しく、なるその他のすべての要因と、"BizTalk: メッセージング遅延/要求-応答の待機時間 (秒)"BizTalk Server 環境で使用する BizTalk Server コンピューターが物理ハードウェアにインストールされていたときに 66.9% からパフォーマンス モニター カウンターが 94.3% 達成可能な待機時間の範囲します。  
  
 ときに、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]環境内のコンピューターが HYPER-V 仮想マシンにインストールされた、ソリューションのスループットが大幅に低下する検出された、このスループットの低下は、で、HYPER-Vに必要なCPUオーバーヘッドに原因があります。[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]仮想マシン。  
  
### <a name="sql-server-processor-utilization-and-batch-requests-per-second-sample-results"></a>SQL Server のプロセッサ使用率と 2 つ目のサンプル結果ごとにバッチ要求  
 SQL Server のプロセッサ使用率 \SQL\Processor(_Total) によって測定される\\% Processor Time カウンターが約 88% 低から 90.1% の値が高くに至るまで、すべてのテスト環境で同じです。 ありませんが、\SQL Server:SQL Statistics\Batch 間に大きな違い要求数/秒が統合された環境 (4520) で測定され、物理環境 (6350) で、\SQL Server:SQL Statistics\Batch 要求数/秒の測定します。 \SQL Server:SQL Statistics\Batch 要求数/秒パフォーマンス モニター カウンターは、SQL Server によって実行される作業量を示す優れた指標を提供します。 バッチ要求/秒、HYPER-V 環境で SQL Server が実行されている場合、削減は、HYPER-V で必要な CPU オーバーヘッドに原因があります。  
  
### <a name="biztalk-server-and-sql-server-network-throughput-sample-results"></a>BizTalk Server と SQL Server ネットワークのスループットのサンプルの結果  
 HYPER-V 仮想マシンで実行されている BizTalk Server のネットワーク スループットはから約 70 ~ 96%、特定のテスト環境に応じて、物理 BizTalk サーバーで行うこと、ネットワーク スループットの範囲に確認されました。 HYPER-V 仮想マシンで実行されている SQL Server のネットワーク スループットがから約 68% から 81% のネットワーク スループットを特定のテスト環境に応じてもう一度、物理 SQL Server で行うことの範囲に確認されました。 観察されたネットワークのスループット単位のデルタは、HYPER-V ハイパーバイザーのリソース要件に起因ことができます。  
  
### <a name="biztalk-server-and-sql-server-available-memory-sample-results"></a>BizTalk Server と SQL Server の使用可能なメモリ サンプル結果  
 SQL Server と \Memory\Available Mbytes パフォーマンス モニター カウンターによって測定される、BizTalk Server に使用できる合計メモリは、すべてのテスト シナリオは一貫性でした。