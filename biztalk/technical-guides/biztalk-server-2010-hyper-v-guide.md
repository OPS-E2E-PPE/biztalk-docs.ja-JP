---
title: BizTalk Server 2010 HYPER-V ガイド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c38ecdd-de72-41d9-b639-2aa6bbfee917
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb61f489eb22bcd2c73be3c528c788d97d23878
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399304"
---
# <a name="biztalk-server-2010-hyper-v-guide"></a>BizTalk Server 2010 HYPER-V ガイド
このガイドの目的は、Microsoft と Microsoft BizTalk Server を使用するための実用的なガイダンスを提供する[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]HYPER-V。 強調[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がパフォーマンスの評価方法とパフォーマンス テストのシナリオでは一般に仮想化されたサーバー アプリケーションのパフォーマンスを分析するために便利です。 このガイダンスは、IT プロフェッショナルと開発者のコミュニティを対象になります。  

 このガイドのコピーをダウンロードするには[ http://go.microsoft.com/fwlink/?LinkId=149267](http://go.microsoft.com/fwlink/?LinkId=149267)します。  

## <a name="introduction"></a>概要  
 サーバー仮想化は、1 つの物理マシン上の複数のオペレーティング システムを実行する機会を企業に提供します。 これにより、少数の完全に使用されているコンピューター上に使用率が低いサーバーの統合。 仮想化を実装すると、企業は運用最小限に抑えるし、資本コストを展開し、エンタープライズ アプリケーションに必要なサーバーの運用に関連付けられています。  

 潜在的なコスト削減には、サーバー仮想化に適した候補を識別するために、新規および既存のアプリケーションを評価する IT 部門が求めるメッセージが表示します。 このような最も評価は、仮想化の総コストを検出するシークします。 仮想化の総コストは、ハードウェアと、IT オペレーションの金銭的コストと物理的な環境で達成可能なパフォーマンスと比較して、仮想化のパフォーマンス コストの合計です。 このガイドでは、仮想化のパフォーマンスの側面にのみ焦点を当てています。  

 以降 Windows Server 2008 では、HYPER-V テクノロジを使用してサーバーの仮想化されたオペレーティング システムの不可欠な部分です。 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] HYPER-V では、サーバー使用率の向上し、コストの削減組織にもたらす信頼性の高い、最適化された仮想化ソリューションを提供します。 ライブ マイグレーション機能、拡張プロセッサおよびメモリのサポートをホスト システムでは、動的な仮想マシンの記憶域のサポートなどの新機能の追加の 単一の物理サーバーにワークロードを統合することが可能し、は、開発およびテスト環境の場合と同様にサーバーの統合が組織に最適なソリューションです。  

 BizTalk Server は最新の仮想化の機能強化の一部として含まれている[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]につながることが、HYPER-V を実稼働サーバーの統合とビジネス継続性管理、および動的な詳細の作成コストの削減IT インフラストラクチャ。 クラスタ リング機能には、追加のソフトウェアまたはハードウェアなしのマルチサイト クラスタ リング環境で展開する BizTalk Server ができます。 HYPER-V の仮想化されたインスタンスで BizTalk Server の複数のインスタンスを実行するサポートを提供する[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]します。 サーバー仮想化は、BizTalk に安全な方法で使用率が低いリソースを統合することで、BizTalk 展開のハードウェアの占有領域を最小限に抑えます。  

 BizTalk Server の展開は通常、数を含むその他のコンポーネントで構成されます。SQL Server、Windows Server、およびインターネット インフォメーション サービス (IIS)。 HYPER-V では、現実的なシナリオをオンデマンドでプロビジョニングする System Center Virtual Machine Manager (VMM) での動的プロビジョニングのサポートを提供します。  

 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 1 台の物理サーバー上に複数のオペレーティング システム インスタンスの仮想化によるサーバーの統合を対応するために HYPER-V テクノロジを提供します。 コア部分として、HYPER-V が提供される[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]または組織内の仮想化を採用するお客様にとってできるだけ簡単にするスタンドアロン製品として。 HYPER-V を実装するためのいくつかの主要シナリオします。  

- **サーバーの統合**– 運用サーバー フット プリントと資本 (TCO) を 1 つのボックスに複数の物理サーバーを統合することでアプリケーションの実行に関連付けられているを最小化します。  

- **テストと開発**– 仮想マシンを使用して、開発者やアーキテクト迅速にプロビジョニングできる新しいマシンの新しいテクノロジおよび物理環境の特性を正確に反映する安全な環境でのシナリオを試します。 仮想化により新しいマシンをプロビジョニングする新しいハードウェアが必要になることがなく、オペレーティング システムの幅広いプラットフォームで実行されています。 これは、テストと開発環境の優れたプラットフォームを提供します。  

- **ビジネス継続性とディザスター リカバリー** – HYPER-V には、強力なビジネス継続性が含まれていて、ディザスター リカバリー機能により、そのサービス レベル契約を満たすためにバックアップし、クイック移行を live など。  

  > [!NOTE]  
  >  HYPER-V 仮想マシンが Windows Server バックアップを使用して、バックアップには、マイクロソフト サポート技術情報を表示する方法については、958662 の記事「Windows を使用して Windows Server 2008 ベース コンピューターにある親パーティションからの HYPER-V 仮想マシンをバックアップする方法サーバーのバックアップ"で[ http://go.microsoft.com/fwlink/?LinkId=131207](http://go.microsoft.com/fwlink/?LinkId=131207)します。  
  >   
  >  HYPER-V ライブ移行機能は、Windows Server 2008 R2 で利用可能なを使用する方法については、"HYPER-V を参照してください。Windows Server 2008 R2 でライブ マイグレーションを使用するステップ バイ ステップ ガイド」で[ http://go.microsoft.com/fwlink/?LinkID=139667](http://go.microsoft.com/fwlink/?LinkID=139667)します。  

- **動的なデータ センター** – HYPER-V をツールの Microsoft System Center スイートを組み合わせることにより、組織を仮想マシンの構成と監視自動化できます。 詳細についてを参照してください"System Center Virtual Machine Manager の" [ http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303)します。  

  このガイドの情報は、hyper-v サーバーの統合、テストおよび開発のシナリオに直接関連します。 他の 2 つは、このガイドの対象外でした。  

  HYPER-V の主要なシナリオの詳細については、次を参照してください[hyper-v で仮想化。概要](http://go.microsoft.com/fwlink/?LinkID=202438)と、トピック、 [Appendices1](../technical-guides/appendices1.md)このガイドの「します。  

### <a name="who-should-read-this"></a>読者でしょうか。  

- 使用するすべての IT プロフェッショナル [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  

- 展開、最適化、およびアプリケーション環境を管理する IT プロフェッショナル  

- IT プロフェッショナルを評価し、システム アーキテクチャを最適化する開発チームと協力  

- 作成および管理する開発者[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション  

- パフォーマンスの最適化とパフォーマンスのボトルネックの特定の関心のある開発者  

### <a name="goals-of-this-guide"></a>このガイドの目的  
 このガイドの主な目的は、HYPER-V で実行されている BizTalk Server がパフォーマンス要件に対応する可能性を判断する方法についてのガイダンスを提供します。 このガイダンスは、展開済みの最適化を支援するための値のするも[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。  

 このプロジェクトは、次の目的で実施されています。  

- 評価、設計、または、仮想化の実装したすべてのユーザーの特定のガイダンスを提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  

- パフォーマンス モニター カウンターおよび仮想化されたサーバー プラットフォームのパフォーマンス能力を測定するためのツールを紹介します。  

- 物理および仮想化サーバー環境のパフォーマンスの差の関数として仮想化のコストを判断するためのガイドラインを提供します。  

- 計画したり、仮想化を最適化するときに使用するためのベスト プラクティスを開発[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  

- デプロイする方法を判断するのに役立つアーキテクチャ ガイダンスを提供[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仮想環境にします。  

- 識別し、仮想化環境でパフォーマンスのボトルネックを文書化します。  

### <a name="whats-in-this-guide"></a>このガイドでは  
 実装するためのガイダンスを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HYPER-V 仮想化環境でのソリューションです。 このガイドは次のとおりです。  

- **BizTalk Server を HYPER-V に展開する**:[HYPER-V での BizTalk Server の展開](../technical-guides/deploying-biztalk-server-on-hyper-v.md)のパフォーマンスを比較するために使用するラボ環境をセットアップするために行った手順を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を同じ HYPER-V 仮想マシンで実行されているソリューション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で実行されているソリューション物理ハードウェアです。  

- **Hyper V 上の BizTalk Server のパフォーマンスを評価する**:[HYPER-V での BizTalk Server のパフォーマンスを評価する](../technical-guides/evaluating-biztalk-server-performance-on-hyper-v.md)のパフォーマンスを測定するときに重要な考慮事項の詳細、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションは、HYPER-V 仮想化環境で実行されています。  

- **Hyper V 上の BizTalk Server のパフォーマンスをテストする**:[BizTalk Server の仮想化のパフォーマンスをテストする](../technical-guides/testing-biztalk-server-virtualization-performance.md)のパフォーマンスを比較する 4 つの異なるテスト シナリオの詳細な結果を提供します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を同じ HYPER-V 仮想マシンで実行されているソリューション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション物理ハードウェア上で実行されています。  

- **付録**:トピックでは、 [Appendices1](../technical-guides/appendices1.md)など、このガイドの重要な参照資料を提供します。  

  -   [付録 a:テスト環境内のコンピューターを最適化適用](../technical-guides/appendix-a-optimizations-applied-to-computers-in-test-environment.md)– テスト環境内のコンピューターに適用されていたパフォーマンスの最適化に関する詳細な情報を提供します。  

  -   [付録 b:HYPER-V のアーキテクチャと機能の概要](../technical-guides/appendix-b-hyper-v-architecture-and-feature-overview.md)- HYPER-V アーキテクチャの概要を説明します、ハイパー-V の長所と短所について説明し、HYPER-V と Virtual Server 2005 の違いについて説明します  

  -   [付録 c:BizTalk Server と SQL Server、HYPER-V のサポート性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)–、HYPER-V 仮想マシンで BizTalk Server と SQL Server を実行するためのサポート ポリシーをについて説明します。  

  -   [付録 d:パフォーマンスを測定するためのツール](../technical-guides/appendix-d-tools-for-measuring-performance.md)-監視し、BizTalk Server 環境のパフォーマンスの評価に使用できるいくつかのツールについて説明します。  

- **用語集**:[Glossary8](../technical-guides/glossary8.md)このガイドで使用される主な用語を定義します。
