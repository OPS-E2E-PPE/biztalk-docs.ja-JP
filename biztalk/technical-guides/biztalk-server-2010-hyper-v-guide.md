---
title: "BizTalk Server 2010 の HYPER-V のガイド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c38ecdd-de72-41d9-b639-2aa6bbfee917
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0e76fee8ce74f11ec0f1a14334447114f3c4ed0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-2010-hyper-v-guide"></a>BizTalk Server 2010 の HYPER-V のガイド
このガイドの目的は、Microsoft の使用に関する実用的なガイダンスを提供する[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]microsoft [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] HYPER-V です。 強調[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がパフォーマンスの評価方法とパフォーマンスのテストのシナリオは一般に、仮想化サーバー アプリケーションのパフォーマンスを分析するために役立ちます。 このガイドは、IT 技術者と開発者コミュニティへの関心のあるされます。  
  
 このガイドのコピーをダウンロードするには[http://go.microsoft.com/fwlink/?LinkId=149267](http://go.microsoft.com/fwlink/?LinkId=149267)です。  
  
## <a name="introduction"></a>概要  
 サーバー仮想化は、単一の物理コンピューターに複数のオペレーティング システムを実行する機会を企業に提供します。 これにより、使用率が低いサーバーを完全に使用されているマシンの数を減らしてを統合できます。 仮想化を実装すると、企業は運用最小限に抑えるし、経費のコストを展開し、エンタープライズ アプリケーションに必要なサーバーを運用に関連付けられています。  
  
 潜在的なコスト削減はサーバー仮想化に適した候補を特定の新規および既存のアプリケーションを評価すると共に、IT 部門の入力を求めです。 このような最も評価は、仮想化の総コストを検出するシークします。 仮想化の総コストは、ハードウェアおよび IT 操作では、通貨のコストと、物理環境で達成可能なパフォーマンスと比較して仮想化のパフォーマンス コストの合計です。 このガイドでは、仮想化のパフォーマンスの面にのみ焦点を当てています。  
  
 Windows Server 2008 以降では、HYPER-V テクノロジを使用してサーバー仮想化されたオペレーティング システムの重要な一部です。 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]HYPER-V では、企業サーバーの使用率を向上し、コストの削減を有効にして、信頼できる最適化された仮想化ソリューションを提供します。 ライブ マイグレーション機能、拡張されたプロセッサおよびメモリ サポート ホスト システムでは、動的な仮想マシンの記憶域のサポートなどの新機能の追加により、組織は単一の物理サーバー上にワークロードを統合し、開発およびテスト環境の場合と同様にサーバーを統合した組織に適してします。  
  
 BizTalk Server は、最新の仮想化の機能強化の一部として含まれる[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]HYPER-V は、基になることができますを実稼働サーバーの統合とビジネス継続性の管理、および詳細動的の作成のコストの削減IT インフラストラクチャです。 クラスタ リング機能では、追加のソフトウェアまたはハードウェアせずマルチサイト クラスタ リング環境に展開される BizTalk Server。 HYPER-V の仮想化されたインスタンスで BizTalk Server の複数のインスタンスを実行するサポートを提供する[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]です。 サーバー仮想化は、BizTalk を安全な方法で過小使用されたリソースの統合による BizTalk 展開のハードウェアの使用量を最小限に抑えます。  
  
 BizTalk Server の展開を含むその他のコンポーネントの数の通常で構成されています。 SQL Server、Windows Server インターネット インフォメーション サービス (IIS)。 HYPER-V では、動的、現実的なシナリオをオンデマンドでプロビジョニング System Center Virtual Machine Manager (VMM) 経由のプロビジョニングのサポートを提供します。  
  
 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]により、単一の物理サーバー上に複数のオペレーティング システムのインスタンスの仮想化サーバーの統合、それに合わせて HYPER-V テクノロジを提供します。 HYPER-V のコア部分として提供[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]または自分の組織での仮想化を導入するお客様できるだけ簡単にスタンドアロン製品として。 Hyper-v: を実装するためのいくつかの主要シナリオします。  
  
-   **サーバーの統合**– server のフット プリント、運用と経費 (TCO) を 1 つのボックスに複数の物理サーバーを統合することでアプリケーションの実行に関連付けられているを最小化します。  
  
-   **テストと開発**– 仮想マシンを使用して、開発者、アーキテクト迅速にマシンをプロビジョニングできます新しい新しいテクノロジおよびシナリオ物理環境の特性を正確に反映されている安全な環境で試してみてください。 仮想化をプロビジョニングする新しいマシンを新しいハードウェアが必要になることがなく、オペレーティング システムの幅の広いプラットフォームで実行します。 これは、テストおよび開発環境の優れたプラットフォームを提供します。  
  
-   **ビジネス継続性と災害復旧**– HYPER-V は強力なビジネス継続性と災害復旧機能により、そのサービス レベル契約に対応するバックアップとクイック移行をライブなどです。  
  
    > [!NOTE]  
    >  Windows Server バックアップを使用して HYPER-V 仮想マシンをバックアップには、Microsoft サポート技術情報を表示する方法に関する情報の記事 958662、"Windows を使用して Windows Server 2008 ベースのコンピューター上の親パーティションからの HYPER-V 仮想マシンをバックアップする方法サーバーのバックアップ"で[http://go.microsoft.com/fwlink/?LinkId=131207](http://go.microsoft.com/fwlink/?LinkId=131207)です。  
    >   
    >  HYPER-V のライブ移行機能は、Windows Server 2008 R2 で利用可能なを使用する方法についてを参照してください"Hyper-v: ステップ バイ ステップ ガイドを使用してライブ移行で Windows Server 2008 R2" [http://go.microsoft.com/fwlink/?LinkID=139667](http://go.microsoft.com/fwlink/?LinkID=139667)です。  
  
-   **動的データ センター** : HYPER-V を Microsoft System Center 用ツール群を組み合わせることにより、組織を仮想マシンの構成と監視自動化できます。 詳細についてを参照してください"System Center Virtual Machine Manager" [http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303)です。  
  
 このガイドの情報は、直接、HYPER-V のサーバーを統合し、テストと開発のシナリオに関連します。 他の 2 つは、このガイドのスコープ外でした。  
  
 HYPER-V の主なシナリオの詳細については、次を参照してください。[の仮想化と hyper-v の概要](http://go.microsoft.com/fwlink/?LinkID=202438)およびトピックでは、、 [Appendices1](../technical-guides/appendices1.md)このガイドの「します。  
  
### <a name="who-should-read-this"></a>これを読み取るユーザー必要がありますか。  
  
-   作業しているすべての IT プロフェッショナル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   を展開する IT 担当者は、最適化し、アプリケーション環境の管理  
  
-   評価し、システムのアーキテクチャを最適化する開発チームと協力する IT 担当者  
  
-   作成および管理する開発者[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション  
  
-   パフォーマンスの最適化とパフォーマンスのボトルネックの特定の興味のある開発者  
  
### <a name="goals-of-this-guide"></a>このガイドの目的  
 このガイドの主な目的を確認する方法に関するガイダンスを提供する[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]を期待されるパフォーマンスを達成できそうは HYPER-V で実行されています。 このガイダンスもされます値の展開済みの最適化に役立てるために[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションです。  
  
 このプロジェクトは、次の目的で実施されました。  
  
-   評価する、設計、または、仮想化を実装したすべてのユーザーの具体的なガイダンスを提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
-   パフォーマンス モニター カウンターおよび仮想化サーバー プラットフォームのパフォーマンス能力を測定するためのツールの概要を提供します。  
  
-   物理および仮想サーバー環境のパフォーマンスの差の関数として仮想化のコストを判断するためのガイドラインを提供します。  
  
-   開発の計画や、仮想化を最適化するときに使用するためのベスト プラクティス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
-   展開する方法を決定するためのアーキテクチャに関するガイダンスを提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を仮想環境でします。  
  
-   識別し、仮想化環境でパフォーマンスのボトルネックを文書化します。  
  
### <a name="whats-in-this-guide"></a>このガイドで何ですか。  
 実装するためのガイダンス、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 仮想化環境でソリューションです。 このガイドは次のとおりです。  
  
-   **HYPER-V での BizTalk Server を展開する**: [HYPER-V 上の BizTalk Server の展開](../technical-guides/deploying-biztalk-server-on-hyper-v.md)のパフォーマンスを比較するために使用するラボ環境をセットアップするために行った手順について説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で実行されているソリューションHYPER-V 仮想マシンを同じ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]物理ハードウェア上で実行されているソリューションです。  
  
-   **HYPER-V での BizTalk Server のパフォーマンスを評価する**: [HYPER-V 上の BizTalk サーバー パフォーマンスの評価](../technical-guides/evaluating-biztalk-server-performance-on-hyper-v.md)のパフォーマンスを測定するときに重要な考慮事項の詳細、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を HYPER-V で実行されているソリューション仮想化された環境です。  
  
-   **HYPER-V での BizTalk Server のパフォーマンスをテストする**: [BizTalk サーバー仮想化のパフォーマンスのテスト](../technical-guides/testing-biztalk-server-virtualization-performance.md)のパフォーマンスを比較する 4 つの異なるテスト シナリオの詳細な結果を提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]同じ HYPER-V 仮想マシンで実行されているソリューション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]物理ハードウェア上で実行されているソリューションです。  
  
-   **付録**: トピックでは、 [Appendices1](../technical-guides/appendices1.md)など、このガイドについての重要な参考資料を提供します。  
  
    -   [付録 a: テスト環境のコンピューターに最適化適用](../technical-guides/appendix-a-optimizations-applied-to-computers-in-test-environment.md)– テスト環境内のコンピューターに適用されていたパフォーマンスの最適化に関する詳細な情報を提供します。  
  
    -   [付録 b: HYPER-V のアーキテクチャと機能の概要](../technical-guides/appendix-b-hyper-v-architecture-and-feature-overview.md)- HYPER-V アーキテクチャの概要を示します、HYPER-V の長所と短所について説明します、HYPER-V と Virtual Server 2005 の違いについて説明します  
  
    -   [付録 c: BizTalk Server と SQL Server の HYPER-V でサポート](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)– HYPER-V 仮想マシンで BizTalk Server と SQL Server を実行するためのサポート ポリシーをについて説明します。  
  
    -   [付録 d: ツールのパフォーマンスの測定を](../technical-guides/appendix-d-tools-for-measuring-performance.md)-を監視し、BizTalk Server 環境のパフォーマンスを評価するために使用できるいくつかのツールについて説明します。  
  
-   **用語集**: [Glossary8](../technical-guides/glossary8.md)このガイドで使用される主な用語を定義します。