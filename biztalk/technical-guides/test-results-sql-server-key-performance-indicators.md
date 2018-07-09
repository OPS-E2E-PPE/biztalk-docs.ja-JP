---
title: 'テスト結果: SQL Server の主要業績評価指標 |Microsoft Docs'
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
ms.openlocfilehash: ed7f1348a23e6c4b145748ccfc0832c97648bdff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007515"
---
# <a name="test-results-sql-server-key-performance-indicators"></a>テスト結果: SQL Server の主要業績評価指標
このトピックでは、SQL サーバー主要業績評価指標 (KPI) テスト シナリオの中に確認されたをまとめたものです。 これらのテストには、次の SQL Server KPI が評価されます。  
  
-   SQL のプロセッサ使用率によって測定される、 **\SQL\Processor(_Total)\\% Processor Time**パフォーマンス モニター カウンター。  
  
-   TRANSACT-SQL コマンド バッチの数の受信/秒で測定した、 **\SQL Server:SQL Statistics\Batch 要求数/秒**パフォーマンス モニター カウンター。  
  
## <a name="summary-of-sql-server-key-performance-indicators"></a>SQL Server の主要業績評価指標の概要  
 各シナリオの物理マシンは、論理プロセッサと仮想プロセッサの数が対応できるように制限されていました。 これは/maxmem および/numproc の boot.ini スイッチを使用します。 詳細については、これらのスイッチを使用して、参照してください「ブート INI オプションの参照」 [ http://go.microsoft.com/fwlink/?LinkId=122139](http://go.microsoft.com/fwlink/?LinkId=122139)します。  
  
 **SQL Server 主要業績評価指標 – の比較**[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]プロセッサ使用率によって測定される**\SQL\Processor(_Total)\\% Processor Time**カウンターが約で同じでは、すべてのテスト88% 低から 90.1% の値が高くに至るまでの環境。   ただしがある間に大きな違い、 **\SQL Server:SQL Statistics\Batch 要求数/秒**統合環境 (4520) で計測と**\SQL Server:SQL Statistics\Batchの要求/秒**物理環境 (6350) 上で計測されます。 **\SQL Server:SQL Statistics\Batch 要求数/秒**パフォーマンス モニター カウンターは、SQL Server によって実行される作業量を示す優れた指標を提供します。 バッチ要求/秒、HYPER-V 環境で SQL Server が実行されている場合、削減は、HYPER-V で必要な CPU オーバーヘッドに原因があります。  
  
 ただし、大きな違い、 **\SQL Server:SQL Statistics\Batch 要求数/秒**統合環境 (4520) で測定し、 **\SQL Server:SQL Statistics\Batch 要求数/秒**物理環境 (6350) 上で計測されます。 **\SQL Server:SQL Statistics\Batch 要求数/秒**パフォーマンス モニター カウンターは、SQL Server によって実行される作業量を示す優れた指標を提供します。 バッチ要求/秒、HYPER-V 環境で SQL Server が実行されている場合、削減は、HYPER-V で必要な CPU オーバーヘッドに原因があります。  
  
 以下の手順によって測定される、HYPER-V 仮想マシンで実行されている SQL Server のパフォーマンスを向上させる、 **\SQL Server:SQL Statistics\Batch 要求数/秒**パフォーマンス モニター カウンター。  
  
1. **専用仮想コント ローラーとチャネル – 追加の固定 VHD ディスクを割り当てる**を使用して追加の固定 VHD ディスクの割り当ては専用の仮想コント ローラーとチャネルの 1 つの VHD ディスクを使用すると、ディスクのスループットが増加します。  
  
2. **ネットワークのパフォーマンスを最適化**の「ネットワークのパフォーマンスを最適化する」セクションに記載されている手順に従います[チェックリスト: hyper-v のパフォーマンスの最適化](~/technical-guides/checklist-optimizing-performance-on-hyper-v.md)します。 「同じ Hyper-v ホストで実行されている構成、HYPER-V 仮想マシンは、プライベート仮想ネットワークを使用するコンピューターをホスト」セクションで推奨事項に従ってに特に重要なは、同じ HYPER-V ホスト上の複数の HYPER-V 仮想マシンを実行している場合[ネットワーク最適化](../technical-guides/network-optimizations.md)します。  
  
   ステートレスな性質のため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追加[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]仮想マシンできます簡単に環境に追加して、スケール アウトを行い、システムの全体的なパフォーマンスを向上するためにします。  
  
   次の図は、テストするさまざまなプラットフォーム上の SQL Server のパフォーマンスを示しています。  
  
   ![SQL 主要業績評価指標](../technical-guides/media/sqlkpi.gif "SQLKPI")  
   SQL 主要業績評価指標  
  
   次の表は、収集された KPI の各構成の相対的なパフォーマンスを示しています。 各結果セットは KPI のベースライン構成の割合として計算されます。  
  
|KPI (KPI)|仮想 BizTalk/物理 SQL|個別のホスト上の仮想 BizTalk/仮想 SQL|統合環境で仮想 BizTalk/仮想 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|\SQL\Processor(_Total)\\プロセッサ時間の割合|97.7%|98.4%|99.9%|  
|\SQL server: SQL Statistics\Batch 要求/秒|97.1%|83.3%|71.2%|  
  
 ディスク I/O パフォーマンスを評価する方法の詳細については、次を参照してください。、**ディスク I/O パフォーマンスを測定する**」の「[チェックリスト: Hyper-v のパフォーマンスを測定する](../technical-guides/checklist-measuring-performance-on-hyper-v.md)します。  
  
 SQL Server 2008 を HYPER-V 環境で実行する場合のベスト プラクティスの詳細については、「を実行している SQL Server 2008 in a HYPER-V 環境 – ベスト プラクティスとパフォーマンスに関する推奨事項」ダウンロードできるホワイト ペーパーを参照してください[ 。http://go.microsoft.com/fwlink/?LinkId=144622](http://go.microsoft.com/fwlink/?LinkId=144622).