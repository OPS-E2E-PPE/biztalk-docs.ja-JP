---
title: "テスト結果: BizTalk Server 主要業績評価指標 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 902cdfc1-21ab-4f56-b97b-2f8979514b11
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1205b0ca8a3fa502df1616900bd112546c5b5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="test-results-biztalk-server-key-performance-indicators"></a>テスト結果: BizTalk Server 主要業績評価指標
このトピックでは、BizTalk サーバー主要業績評価指標 (KPI) テスト シナリオで監視された概要を示します。 具体的にはこれらのテスト評価のスループットによって測定される、"**BizTalk: メッセージング ドキュメント処理数/秒**"パフォーマンス モニター カウンター、および待機時間、Visual studio クライアントの応答時間を測定します。  
  
## <a name="summary-of-biztalk-server-key-performance-indicators"></a>BizTalk Server 主要業績評価指標の概要  
 各シナリオの物理コンピューターは、論理プロセッサと仮想プロセッサの数が等価ように制限されていました。 これは、/maxmem と/numproc boot.ini スイッチを使用します。 詳細については、これらのスイッチを使用して、参照してください「ブート INI オプションの参照」 [http://go.microsoft.com/fwlink/?LinkId=122139](http://go.microsoft.com/fwlink/?LinkId=122139)です。  
  
 **BizTalk Server 主要業績評価指標-の比較**を実行している[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]、HYPER-V で仮想マシンが約 95% のスループットと待機時間のパフォーマンスを提供[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]このテスト シナリオの物理ハードウェア上でします。 状態のない性質[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], additional[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]仮想マシンできます簡単に環境に追加して、スケール アウトを提供し、システムの全体的なパフォーマンスを向上するためにします。 作成と追加[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]環境には、基本イメージから新しいイメージを生成する sysprep ユーティリティを使用して実現できます。  
  
> [!NOTE]  
>  Sysprep 応答ファイルとスクリプトで提供されます[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]sysprep を使用して、インストールされているコンピューターの既存のイメージから追加のイメージを作成する、それに合わせて[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]インストールします。 これらのサンプル スクリプトがで使用するために設計された[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]32 ビットおよび 64 ビット バージョンの Windows Server 2008 のみにインストールされています。 詳細については、次を参照してください。、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]オンライン ドキュメントを参照します。  
  
 プロビジョニング、統合、およびバーチャル マシンの管理できますで大幅に優先的 System Center Virtual Machine Manager (VMM) を使用しています。 System Center Virtual Machine Manager に関する詳細については、次を参照してください[http://go.microsoft.com/fwlink/?LinkID=111303。](http://go.microsoft.com/fwlink/?LinkID=111303)  
  
 このパフォーマンス ラボで得られた結果の表示を実行しているときに実現されるパフォーマンスを大幅に強化[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]で[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]HYPER-V 仮想マシンでします。 実行している[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]、HYPER-V で仮想マシンが約 75% のスループットと待機時間のパフォーマンスを提供[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]と物理ハードウェア上で、実行時に約 95% のパフォーマンス低下[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]と[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]HYPER-V 仮想マシン。 このパフォーマンスの向上はほとんどのパフォーマンスの向上に起因する[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]HYPER-V でゲスト オペレーティング システムとして実行するときにします。 関連するパフォーマンスの比較、 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] HYPER-V ガイドについては、「 [http://go.microsoft.com/fwlink/?LinkId=147144](http://go.microsoft.com/fwlink/?LinkId=147144)です。  
  
 次の図は、のパフォーマンスを示しています。[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]さまざまなプラットフォームをテストします。  
  
 ![BizTalk 主要業績評価指標](../technical-guides/media/biztalkkpi.gif "BizTAlkKPI")  
  
 次の表は、収集される KPI のそれぞれの構成の相対的なパフォーマンスを示しています。 各結果セットは、KPI の基準構成の割合として計算されます。  
  
|KPI (KPI)|仮想 BizTalk/物理 SQL|個別のホスト上の仮想 BizTalk/仮想 SQL|統合環境で仮想 BizTalk/仮想 SQL|  
|---------|-----------------------------------|----------------------------------------------------|--------------------------------------------------------------|  
|処理 \BizTalk:Messaging\Documents の数/秒|94.3%|79.8%|67%|  
|Visual Studio クライアントによって測定される遅延時間|94.3%|79.7%|66.9%|  
  
 BizTalk Server ソリューションのパフォーマンスを最適化する方法の詳細については、BizTalk Server パフォーマンス最適化ガイドで使用可能なを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=122477](http://go.microsoft.com/fwlink/?LinkId=122477)です。  
  
## <a name="performance-comparison-results-summary"></a>パフォーマンスの比較結果の概要  
 94.3% スループットと 94.3% の待機時間だけを実行しているときに実現される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 上での HYPER-V を使用して、ソリューションのこの層の仮想化によって提供されている、プロビジョニング、統合、柔軟性、使いと共に、優れたパフォーマンスを提案管理が可能な HYPER-V 環境にソリューションを展開する場合です。  
  
### <a name="throughput-comparison-sample-results"></a>スループットの比較サンプルの結果  
 ときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]によって測定される、BizTalk Server ソリューションのスループット、HYPER-V 仮想マシン上に BizTalk Server 環境で使用されているコンピューターが実行された、"**BizTalk: メッセージング ドキュメント処理数/秒**"パフォーマンス モニターのカウンターの範囲は 67% から 94.3% の達成可能なスループットに物理ハードウェア上のすべての BizTalk Server 環境で使用されているコンピューターにインストールされたときにします。  
  
### <a name="latency-comparison-sample-results"></a>待機時間の比較サンプルの結果  
 ときに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk Server 環境で使用されているコンピューターは HYPER-V 仮想マシン、Visual Studio クライアント応答によって測定される、BizTalk Server ソリューションの待機時間で実行された時間の範囲は 66.9% から 94.3% 達成可能な待機時間のときにすべてBizTalk Server 環境で使用するコンピューターは、物理ハードウェアにインストールされました。