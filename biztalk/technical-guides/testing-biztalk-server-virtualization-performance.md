---
title: "BizTalk Server の仮想化のパフォーマンスのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d09121b1-cdd6-4c01-9d69-0f1923464f0e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cec992ab489c63f68ac4d77652209e65eff258a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="testing-biztalk-server-virtualization-performance"></a>BizTalk Server の仮想化のパフォーマンスをテストします。
Microsoft テスト ラボで物理コンピューターに展開されたそれぞれのこのガイドで説明されているパフォーマンス テストのシナリオと、それぞれ個別のシステム アーキテクチャが同じロード テストが実行されます。 各物理コンピュータ上のホスト オペレーティング システムがのフル インストールであった[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、64 ビット版で、HYPER-V サーバーの役割がインストールされています。 テストに使用する仮想マシン[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]で設定された[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、ゲスト オペレーティング システムと 64 ビット エディションです。 テストに使用する仮想マシン[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]で設定した[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、ゲスト オペレーティング システムと 64 ビット エディションです。 一連のベスト プラクティスとの設計、実装、ガイダンスの策定に使用されたテストのシナリオ、テスト メソッド、パフォーマンス テストの結果、およびその後の分析と仮想化を最適化して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
-   **テストのシナリオ 1: ベースライン**– 最初のシナリオは、物理ハードウェアのみで実行されている BizTalk Server 環境のベースライン パフォーマンスを確立するために設計されました。 このシナリオで BizTalk Server と SQL Server の両方がインストールされているし、のみ、物理ハードウェア上で実行します。  
  
-   **テストのシナリオ 2: 仮想 BizTalk/物理サーバーの SQL Server** -2 番目のシナリオは、同じ物理サーバー上の複数のゲスト仮想マシンで BizTalk Server のホスティングのパフォーマンスの影響を確認するように設計されました。 すべての仮想マシンに分散したテスト結果の構成が、物理マシンの処理に合計数と同数の論理プロセッサと比較し、複数の仮想マシンから取得します。  
  
-   **テスト シナリオ 3: 仮想の BizTalk サーバー/仮想 SQL Server は別の物理的な HYPER-V ホストで**-3 番目のシナリオは、仮想化環境で BizTalk Server と SQL Server の両方を実行するパフォーマンスの影響を判断する実施されています。 ホストされる BizTalk データベースで HYPER-V 仮想マシンで実行される BizTalk Server を使用してテストが実行された、 [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] HYPER-V 仮想マシンで実行されているインスタンス。 このシナリオでは、BizTalk Server の仮想マシンと SQL Server 仮想マシンに別の物理的な HYPER-V ホストでホストされます。  
  
-   **テストのシナリオ 4: サーバーの統合 - 完全 BizTalk グループを含む SQL HYPER-V 上の 1 つの物理サーバー上に統合する**– 1 つの物理サーバーのシナリオでは、すべての仮想マシン (Vm) をテスト アプリケーションを実行する必要がホストされています。 このシナリオの目的は、ホストのパフォーマンス コストを判断する[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]と[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]統合環境で仮想マシン。  
  
 このセクションでは、テスト アプリケーションおよびシナリオごとに使用されるサーバーのアーキテクチャの概要を説明し、主要業績評価指標 (Kpi) のテスト中に観察されたについても説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [テスト シナリオの概要](../technical-guides/test-scenario-overview.md)  
  
-   [テスト シナリオのサーバーのアーキテクチャ](../technical-guides/test-scenario-server-architecture.md)  
  
-   [テスト結果: BizTalk Server 主要業績評価指標](../technical-guides/test-results-biztalk-server-key-performance-indicators.md)  
  
-   [テスト結果: SQL Server の主要業績評価指標](../technical-guides/test-results-sql-server-key-performance-indicators.md)  
  
-   [テスト結果: ネットワー キング主要業績評価指標](../technical-guides/test-results-networking-key-performance-indicators.md)  
  
-   [テスト結果: メモリ主要業績評価指標](../technical-guides/test-results-memory-key-performance-indicators.md)  
  
-   [テスト結果の概要](../technical-guides/summary-of-test-results.md)