---
title: BizTalk Server の仮想化のパフォーマンスのテスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d09121b1-cdd6-4c01-9d69-0f1923464f0e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d45567918cebd18bfea7bf30f31b299f6bed02d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008571"
---
# <a name="testing-biztalk-server-virtualization-performance"></a>BizTalk Server の仮想化のパフォーマンスをテストします。
Microsoft テスト ラボで物理コンピューターに展開されたそれぞれのこのガイドで説明されているパフォーマンス テストのシナリオと、それぞれ個別のシステム アーキテクチャが同じロード テストが実行されます。 各物理コンピュータ上のホスト オペレーティング システムがのフル インストールであった[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、64 ビット版で、HYPER-V サーバーの役割がインストールされています。 BizTalk Server をテストするために使用する仮想マシンに設定された[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、ゲスト オペレーティング システムと 64 ビット エディションです。 SQL Server をテストするために使用するバーチャル マシンで設定した[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、ゲスト オペレーティング システムと 64 ビット エディションです。 一連のベスト プラクティスとの設計、実装、ガイダンスの策定に使用されたテストのシナリオ、テスト メソッド、パフォーマンス テストの結果、およびその後の分析と仮想化を最適化して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
-   **テストのシナリオ 1: ベースライン**– 最初のシナリオは、物理ハードウェアのみで実行されている BizTalk Server 環境のベースライン パフォーマンスを確立するために設計されました。 このシナリオで BizTalk Server と SQL Server の両方がインストールされているし、のみ、物理ハードウェア上で実行します。  
  
-   **テストのシナリオ 2: 仮想 BizTalk/物理サーバーの SQL Server** -2 番目のシナリオは、同じ物理サーバー上の複数のゲスト仮想マシンで BizTalk Server のホスティングのパフォーマンスの影響を確認するように設計されました。 すべての仮想マシンに分散したテスト結果の構成が、物理マシンの処理に合計数と同数の論理プロセッサと比較し、複数の仮想マシンから取得します。  
  
-   **テスト シナリオ 3: 仮想の BizTalk サーバー/仮想 SQL Server は別の物理的な HYPER-V ホストで**-3 番目のシナリオは、仮想化環境で BizTalk Server と SQL Server の両方を実行するパフォーマンスの影響を判断する実施されています。 テストは、HYPER-V 仮想マシンで実行されている SQL Server インスタンスでホストされる BizTalk データベースで HYPER-V 仮想マシンで実行される BizTalk Server を使用して実行されました。 このシナリオでは、BizTalk Server の仮想マシンと SQL Server 仮想マシンに別の物理的な HYPER-V ホストでホストされます。  
  
-   **テストのシナリオ 4: サーバーの統合 - 完全 BizTalk グループを含む SQL HYPER-V 上の 1 つの物理サーバー上に統合する**– 1 つの物理サーバーのシナリオでは、すべての仮想マシン (Vm) をテスト アプリケーションを実行する必要がホストされています。 このシナリオの目的では、SQL Server と統合された環境で BizTalk Server の仮想マシンをホストしている場合のパフォーマンス コストを決定します。  
  
 このセクションでは、テスト アプリケーションおよびシナリオごとに使用されるサーバーのアーキテクチャの概要を説明し、主要業績評価指標 (Kpi) のテスト中に観察されたについても説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [テスト シナリオの概要](../technical-guides/test-scenario-overview.md)  
  
-   [テスト シナリオ サーバーのアーキテクチャ](../technical-guides/test-scenario-server-architecture.md)  
  
-   [テスト結果: BizTalk Server の主要業績評価指標](../technical-guides/test-results-biztalk-server-key-performance-indicators.md)  
  
-   [テスト結果: SQL Server の主要業績評価指標](../technical-guides/test-results-sql-server-key-performance-indicators.md)  
  
-   [テスト結果: ネットワークの主要業績評価指標](../technical-guides/test-results-networking-key-performance-indicators.md)  
  
-   [テスト結果: メモリの主要業績評価指標](../technical-guides/test-results-memory-key-performance-indicators.md)  
  
-   [テスト結果の概要](../technical-guides/summary-of-test-results.md)