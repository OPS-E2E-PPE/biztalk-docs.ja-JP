---
title: BizTalk Server の仮想化のパフォーマンスのテスト |Microsoft Docs
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
ms.openlocfilehash: 3f07c6bf8371e1db84ed574d7c737d4cc5b3903b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993699"
---
# <a name="testing-biztalk-server-virtualization-performance"></a>BizTalk Server の仮想化のパフォーマンスをテストします。
このガイドで説明されているパフォーマンス テストのシナリオが、Microsoft テスト ラボで物理コンピューターで展開され、それぞれ個別のシステム アーキテクチャが、同じロード テストが実行されます。 各物理コンピュータ上のホスト オペレーティング システムがのフル インストール[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、64 ビット版で、HYPER-V サーバーの役割がインストールされています。 BizTalk Server をテストするために使用する仮想マシンを使用して設定された[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、ゲスト オペレーティング システムと 64 ビット エディション。 SQL Server のテストに使用する仮想マシンを使用して設定された[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]Enterprise、ゲスト オペレーティング システムと 64 ビット エディション。 テスト シナリオ、テスト メソッド、パフォーマンス テストの結果、およびその後の分析のベスト プラクティスとガイダンスの設計、実装すると、一連の策定に使用され、仮想化を最適化する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
- **テストのシナリオ 1: ベースライン**– 最初のシナリオでは、物理的なハードウェアのみで実行されている BizTalk Server 環境のベースライン パフォーマンスを確立するために設計されました。 このシナリオで BizTalk Server と SQL Server の両方がインストールされ物理ハードウェアだけで実行します。  
  
- **テストのシナリオ 2: 仮想 BizTalk/物理サーバーの SQL Server** -2 番目のシナリオが同じ物理サーバー上の複数のゲスト仮想マシンで BizTalk Server のホスティングのパフォーマンスに与える影響を判断するように設計されました。 テスト結果の構成が処理の物理マシンと同数の論理プロセッサの合計数を比較し、複数の仮想マシンから取得したすべての仮想マシンに分散します。  
  
- **テスト シナリオ 3: 仮想の BizTalk サーバー/仮想 SQL Server は別々 の物理的な HYPER-V ホスト上**-仮想化環境で BizTalk Server と SQL Server の両方を実行中のパフォーマンスに与える影響を判断する 3 番目のシナリオを行いました。 テストは、HYPER-V 仮想マシンで実行されている SQL Server インスタンスでホストされる BizTalk データベースで、HYPER-V 仮想マシンで実行されている BizTalk Server を使用して実行されました。 このシナリオでは、BizTalk Server の仮想マシンと SQL Server 仮想マシンに別々 の物理 HYPER-V ホストでホストされます。  
  
- **テストのシナリオ 4: サーバーの統合 - 完全な BizTalk グループを含む SQL、HYPER-V 上の 1 つの物理サーバー上に統合する**– 1 つの物理サーバーのシナリオでは、テスト アプリケーションを実行するために必要なすべて仮想マシン (Vm) がホストされています。 このシナリオでは、SQL Server と統合された環境で BizTalk Server の仮想マシン ホストのパフォーマンス コストを判断します。  
  
  このセクションでは、テスト アプリケーションと各シナリオで使用されるサーバーのアーキテクチャの概要を説明し、主要業績評価指標 (Kpi) テスト中に確認されたについても説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [テスト シナリオの概要](../technical-guides/test-scenario-overview.md)  
  
-   [テスト シナリオ サーバーのアーキテクチャ](../technical-guides/test-scenario-server-architecture.md)  
  
-   [テスト結果: BizTalk Server の主要業績評価指標](../technical-guides/test-results-biztalk-server-key-performance-indicators.md)  
  
-   [テスト結果: SQL Server の主要業績評価指標](../technical-guides/test-results-sql-server-key-performance-indicators.md)  
  
-   [テスト結果: ネットワークの主要業績評価指標](../technical-guides/test-results-networking-key-performance-indicators.md)  
  
-   [テスト結果: メモリの主要業績評価指標](../technical-guides/test-results-memory-key-performance-indicators.md)  
  
-   [テスト結果の概要](../technical-guides/summary-of-test-results.md)