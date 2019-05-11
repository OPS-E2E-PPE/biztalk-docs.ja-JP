---
title: テスト結果。BizTalk Server の主要業績評価指標 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 902cdfc1-21ab-4f56-b97b-2f8979514b11
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2499a67156dff5c83be1103c89b94befe6424492
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400641"
---
# <a name="test-results-biztalk-server-key-performance-indicators"></a>テスト結果。BizTalk Server の主要業績評価指標
このトピックでは、BizTalk サーバー主要業績評価指標 (KPI) テスト シナリオの中に確認されたをまとめたものです。 具体的にはこれらのテスト評価によって測定されるスループット、"**BizTalk: メッセージング ドキュメント処理数/秒**"パフォーマンス モニター カウンター、および待機時間、Visual studio クライアントの応答時間で測定されます。  
  
## <a name="summary-of-biztalk-server-key-performance-indicators"></a>BizTalk Server の主要業績評価指標の概要  
 各シナリオの物理マシンは、論理プロセッサと仮想プロセッサの数が対応できるように制限されていました。 これは/maxmem および/numproc の boot.ini スイッチを使用します。 詳細については、これらのスイッチを使用して、参照してください「ブート INI オプションの参照」 [ http://go.microsoft.com/fwlink/?LinkId=122139](http://go.microsoft.com/fwlink/?LinkId=122139)します。  
  
 **BizTalk Server 主要業績評価指標 – の比較**HYPER-V 仮想マシンで実行されている BizTalk Server は、このテスト シナリオの物理ハードウェア上で BizTalk Server のスループットと待機時間のパフォーマンスの約 95% を提供します。 ステートレスな性質のため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、BizTalk Server の仮想マシンを追加できます簡単に環境に追加して、スケール アウトを行い、システムの全体的なパフォーマンスを向上するためにします。 作成して、環境への他の BizTalk Server の追加は、基本イメージから新しいイメージを生成する sysprep ユーティリティを使用して実現できます。  
  
> [!NOTE]  
>  Sysprep 応答ファイルとスクリプトは、BizTalk Server がインストールされているコンピューターの既存のイメージからその他のイメージを作成する sysprep を使用して対応するために BizTalk Server で提供されるは。 これらのサンプル スクリプトは 32 ビットおよび 64 ビット バージョンの Windows Server 2008 のみにインストールされている BizTalk Server で使用するために設計されています。 詳細については、BizTalk Server のオンライン ドキュメントを参照してください。  
  
 プロビジョニング、統合、および仮想マシンの管理できますが大幅に高速に System Center Virtual Machine Manager (VMM) を使用しています。 System Center Virtual Machine Manager に関する詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303)  
  
 このパフォーマンス ラボで取得した結果の表示を実行しているときに実現されたパフォーマンスを大幅に強化[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]で[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]HYPER-V 仮想マシンでします。 実行している[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]仮想マシンを HYPER-V でのスループットと待機時間のパフォーマンスの約 75% が提供される[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]と物理ハードウェア上で、BizTalk Server を実行するときに約 95% のパフォーマンス低下と[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]HYPER-V 仮想マシン。 このパフォーマンスの向上はほとんどのパフォーマンスの向上に起因する[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]HYPER-V でゲスト オペレーティング システムとして実行するとします。 関連するパフォーマンスの比較、 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] HYPER-V ガイドについては、「 [ http://go.microsoft.com/fwlink/?LinkId=147144](http://go.microsoft.com/fwlink/?LinkId=147144)します。  
  
 次の図は、テストするさまざまなプラットフォーム上の BizTalk Server のパフォーマンスを示しています。  
  
 ![BizTalk 主要業績評価指標](../technical-guides/media/biztalkkpi.gif "BizTAlkKPI")  
  
 次の表は、収集された KPI の各構成の相対的なパフォーマンスを示しています。 各結果セットは、KPI のベースライン構成の割合として計算されます。  
  
|KPI (KPI)|仮想 BizTalk/物理 SQL|個別のホスト上の仮想 BizTalk/仮想 SQL|統合環境で仮想 BizTalk/仮想 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|\BizTalk:Messaging\Documents 処理/秒|94.3%|79.8%|67%|  
|Visual Studio クライアントで測定された待機時間|94.3%|79.7%|66.9%|  
  
 BizTalk Server ソリューションのパフォーマンスを最適化する方法の詳細については、BizTalk Server パフォーマンス最適化ガイドで使用可能なを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=122477](http://go.microsoft.com/fwlink/?LinkId=122477)します。  
  
## <a name="performance-comparison-results-summary"></a>パフォーマンスの比較結果の概要  
 94.3% のスループットと 94.3% の待機時間のみを実行しているときに実現[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 上の提案、HYPER-V を使用して、ソリューションのこの層の仮想化、プロビジョニング、統合、柔軟性、容易さと優れたパフォーマンスを提供します。管理をする場合は、HYPER-V 環境にソリューションをデプロイします。  
  
### <a name="throughput-comparison-sample-results"></a>スループットの比較サンプルの結果  
 ときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]によって測定される、BizTalk Server ソリューションのスループットの HYPER-V 仮想マシンで実行されたコンピューターの BizTalk Server 環境で使用される、"**BizTalk: メッセージング ドキュメント処理数/秒**"パフォーマンス モニター カウンターが物理ハードウェア上のすべての BizTalk Server 環境で使用されるコンピューターにインストールされたときに、達成可能なスループットの 94.3% に 67% から範囲します。  
  
### <a name="latency-comparison-sample-results"></a>待機時間の比較サンプル結果  
 ときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk Server 環境で使用するコンピューターは、Visual Studio クライアント応答によって測定される、BizTalk Server ソリューションの待機時間の HYPER-V 仮想マシンで実行された時間に達成可能な待機時間の 94.3% と 66.9% から範囲すべてBizTalk Server 環境で使用するコンピューターは、物理ハードウェアにインストールされています。