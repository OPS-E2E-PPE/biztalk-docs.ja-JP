---
title: 'テスト結果: SQL Server の主要業績評価指標 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2459ee6d-7a75-4338-ba5c-f42ab673ab87
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93e1f1bdef55ad726c308902062dccff67eeb170
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302466"
---
# <a name="test-results-sql-server-key-performance-indicators"></a>テスト結果: SQL Server の主要業績評価指標
このトピックでは、SQL サーバー主要業績評価指標 (KPI) テスト シナリオで監視された概要を示します。 これらのテストには、次の SQL Server KPI が評価されます。  
  
-   SQL のプロセッサ使用率によって評価される、 **\SQL\Processor(_Total)\\% Processor Time**パフォーマンス モニター カウンターです。  
  
-   によって測定される 1 秒あたりの受信を TRANSACT-SQL コマンド バッチの数、 **\SQL Server:SQL Statistics\Batch 要求数/秒**パフォーマンス モニター カウンターです。  
  
## <a name="summary-of-sql-server-key-performance-indicators"></a>SQL Server の主要業績評価指標の概要  
 各シナリオの物理コンピューターは、論理プロセッサと仮想プロセッサの数が等価ように制限されていました。 これは、/maxmem と/numproc boot.ini スイッチを使用します。 詳細については、これらのスイッチを使用して、参照してください「ブート INI オプションの参照」 [http://go.microsoft.com/fwlink/?LinkId=122139](http://go.microsoft.com/fwlink/?LinkId=122139)です。  
  
 **SQL Server 主要業績評価指標-の比較**[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]プロセッサ使用率によって評価される**\SQL\Processor(_Total)\\% Processor Time**カウンターが約すべてで同じです。88% の低から 90.1% の high までの環境をテストします。   ただしが大きな違い、 **\SQL Server:SQL Statistics\Batch 要求数/秒**統合された環境 (4520) 上で計測されます、 **\SQL Server:SQL Statistics\Batchの要求/秒**物理環境 (6350) 上で計測されます。 **\SQL Server:SQL Statistics\Batch 要求数/秒**パフォーマンス モニター カウンターは、SQL Server によって実行される作業量を示す優れた指標を提供します。 バッチ要求数/秒を HYPER-V 環境で SQL Server が実行されている場合に削減は、HYPER-V で必要な CPU オーバーヘッドを属性付けすることができます。  
  
 ただし、大きな違い、 **\SQL Server:SQL Statistics\Batch 要求数/秒**統合された環境 (4520) 上で計測されます、 **\SQL Server:SQL Statistics\Batch 要求数/秒**物理環境 (6350) 上で計測されます。 **\SQL Server:SQL Statistics\Batch 要求数/秒**パフォーマンス モニター カウンターは、SQL Server によって実行される作業量を示す優れた指標を提供します。 バッチ要求数/秒を HYPER-V 環境で SQL Server が実行されている場合に削減は、HYPER-V で必要な CPU オーバーヘッドを属性付けすることができます。  
  
 によって測定される HYPER-V 仮想マシンで実行されている SQL Server のパフォーマンスを向上する次の手順に従って、 **\SQL Server:SQL Statistics\Batch 要求数/秒**パフォーマンス モニター カウンター。  
  
1.  **専用の仮想コント ローラーとチャネル – 追加の固定 VHD ディスクを割り当てる**を使用して追加の固定 VHD ディスクの割り当ての専用仮想コント ローラーと、チャネルで 1 つの VHD ディスクを使用すると、ディスクのスループットが増加します。  
  
2.  **– ネットワーク パフォーマンスを最適化**の「ネットワークのパフォーマンスを最適化する」セクションに記載されている手順に従います[チェックリスト: HYPER-V でのパフォーマンスの最適化](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)です。 「同じ HYPER-V で実行されている構成 HYPER-V 仮想マシンは、プライベート仮想ネットワークを使用してコンピューターをホスト」セクションの推奨事項に従うに特に重要なは、同じ HYPER-V ホスト上の複数の HYPER-V 仮想マシンを実行している場合[ネットワーク最適化](../technical-guides/network-optimizations.md)です。  
  
 状態のない性質[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], additional[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]仮想マシンできます簡単に環境に追加して、スケール アウトを提供し、システムの全体的なパフォーマンスを向上するためにします。  
  
 次の図は、さまざまなテスト プラットフォームでは、SQL Server のパフォーマンスを示しています。  
  
 ![SQL 主要業績評価指標](../technical-guides/media/sqlkpi.gif "SQLKPI")  
SQL 主要業績評価指標  
  
 次の表は、収集される KPI のそれぞれの構成の相対的なパフォーマンスを示しています。 各結果セットは、KPI の基準構成の割合として計算されます。  
  
|KPI (KPI)|仮想 BizTalk/物理 SQL|個別のホスト上の仮想 BizTalk/仮想 SQL|統合環境で仮想 BizTalk/仮想 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|\SQL\Processor(_Total)\\プロセッサ時間の割合|97.7%|98.4%|99.9%|  
|\SQL server: SQL Statistics\Batch 要求数/秒|97.1%|83.3%|71.2%|  
  
 ディスク I/O パフォーマンスを評価する方法の詳細については、次を参照してください。、**ディスク I/O パフォーマンスの測定**」の「[チェックリスト: Hyper-v でのパフォーマンスの測定](../technical-guides/checklist-measuring-performance-on-hyper-v.md)です。  
  
 SQL Server 2008 を HYPER-V 環境で実行されているときのベスト プラクティスの詳細については、「実行されている SQL Server 2008 in a HYPER-V 環境 – ベスト プラクティスとパフォーマンスの推奨」からダウンロードできるホワイト ペーパーを参照してください[http。://go.microsoft.com/fwlink/しますか?LinkId = 144622](http://go.microsoft.com/fwlink/?LinkId=144622)です。