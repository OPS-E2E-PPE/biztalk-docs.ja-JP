---
title: BizTalk Server の高可用性のシナリオのサンプル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- examples, high availability
- architecture, examples
- high availability, examples
- examples, architecture
- databases, clustering
- architecture, medium distributions
- scaling
- architecture, large distributions
ms.assetid: ad9e3f57-1a23-41c2-82c9-dc8e1b29ed4d
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff4db96e89dc91ee96aaf5f0b60f0de34ce83425
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271666"
---
# <a name="sample-biztalk-server-high-availability-scenarios"></a>BizTalk Server の高可用性を実現するサンプル シナリオ
このトピックは、ホストをスケールアウトすることによって Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の高可用性を実現するシナリオについて説明します。 管理者は、それぞれの機能領域を [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の異なるホストおよび層に分離することにより、各ホストの冗長性を確保し、他のホストから独立して個別に拡張することができます。 各機能領域の高可用性を実現するには、主要な機能 (受信、処理、送信、および追跡) ごとに別々のホストを作成し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースとエンタープライズ シングル サインオンのマスター シークレット サーバーをクラスター化します。  
  
## <a name="small-biztalk-server-deployments"></a>BizTalk Server の小規模な展開  
 SQL Server と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の両方に高可用性を確保する最小限の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境には、SQL Server をアクティブ/アクティブのクラスター構成で実行する 2 台のコンピューターを使用します。 この場合、両方のコンピューターが、BizTalk 環境のホスト インスタンスをすべて実行することになります。 1 台のコンピューターでエラーや障害が発生した場合、もう 1 台のコンピューターが、SQL Server と BizTalk Server の両方のサービスを引き継ぎます。 この構成はマスター シークレット サーバーのクラスター化に対応していないため、可用性はあまり高くありません。クラスター化されたエンタープライズ シングル サインオン リソースが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターでパッシブになっていて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホスト インスタンスが起動しないからです。 マスター シークレット サーバーをクラスタ リングの詳細については、次を参照してください。[エンタープライズ シングル サインオンの高可用性](../core/high-availability-for-enterprise-single-sign-on.md)です。  
  
 5 台未満のコンピューターから成る小規模な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境では、BizTalk Server のデータベースをホストする SQL Server クラスターを、BizTalk Server コンピューターとは別のコンピューターで実行することをお勧めします。 BizTalk Server コンピューターでは、すべての BizTalk ホスト (受信、処理、および送信) を実行することができます。 この環境で高可用性を実現するには、SQL Server とエンタープライズ シングル サインオンのマスター シークレット サーバーをクラスター化して 2 つの BizTalk Server を用意し、それぞれが各ホストのインスタンスを実行するように構成します。  
  
 次の図は、小規模な BizTalk Server 環境に高可用性を実現した例を示しています。  
  
 ![BizTalk Server の小規模展開](../core/media/tdi-highava-smalldepl.gif "TDI_HighAva_SmallDepl")  
  
## <a name="medium-sized-biztalk-server-deployments"></a>BizTalk Server の中規模な展開  
 5 台から 10 台のコンピューターから成る中規模の環境では、BizTalk Server データベースとエンタープライズ シングル サインオンのマスター シークレット サーバーをホストする SQL Server をクラスター化することをお勧めします。 受信の負荷が大きい場合、受信ホストのインスタンスを実行する専用の BizTalk Server を 2 つ用意することによって高可用性を確保できます。 さらに、処理と送信の両方のホスト インスタンスを実行する 2 台のコンピューターを追加します。 この環境に高可用性を実現するためには、2 つの BizTalk Server に対し、処理と送信の両方のホスト インスタンスを作成します。 同様に、処理の負荷が大きい場合は、処理ホストのインスタンスを実行する専用の BizTalk Server を 2 つ用意し、残りの 2 つの BizTalk Server で、受信ホストおよび送信ホストの両方のインスタンスを実行するように構成します。  
  
 次の図は、中規模の BizTalk Server 環境で、受信機能を 2 つの BizTalk Server で実行することによって高可用性を実現する例を示しています。  
  
 ![Medium &#45;BizTalk Server の展開の規模](../core/media/tdi-highava-meddepl.gif "TDI_HighAva_MedDepl")  
  
 エンタープライズ シングル サインオンの高可用性の詳細については、次を参照してください。[エンタープライズ シングル サインオンの高可用性](../core/high-availability-for-enterprise-single-sign-on.md)です。  
  
## <a name="large-scale-biztalk-server-deployments"></a>BizTalk Server の大規模な展開  
 10 台以上のコンピューターが存在する大規模な環境では、受信、処理、送信の各機能ごとに専用の BizTalk Server コンピューターを用意します。 また、グループ内に多数の BizTalk Server コンピューターが存在する場合は、メッセージ ボックス データベース コンピューターを追加してパフォーマンスを強化できます。 この場合、メッセージ ボックス データベースとマスター シークレット サーバーをクラスター化することで、高可用性が実現します。  
  
 このような分散構成では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の柔軟性が最大限に発揮されます。環境内で障害の発生しやすい箇所を調べて特定し、戦略に基づいてリソースを割り当て、システムの障害発生点を減らしていくことができるためです。 変化の激しい今日のビジネス環境では、ワークロードやビジネス要件も日々変化するため、こうした柔軟性が不可欠です。  
  
 リソース消費の低いコンピューターから、リソース消費の激しいコンピューターへとリソースを移すことにより、既存のリソースを活用して高可用性を実現することができます。アップグレードや新しいハードウェアを購入するために投資を繰り返す必要はありません。  
  
 次の図は、大規模な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境における構成例を示しています。  
  
 ![大規模な & #45 です。BizTalk Server の展開をスケール](../core/media/tdi-highava-largedepl.gif "TDI_HighAva_LargeDepl")  
  
 エンタープライズ シングル サインオンの高可用性の詳細については、次を参照してください。[エンタープライズ シングル サインオンの高可用性](../core/high-availability-for-enterprise-single-sign-on.md)です。  
  
## <a name="providing-high-availability-using-hyper-v-and-failover-clustering"></a>Hyper-V とフェールオーバー クラスタリングによる高可用性の実現  
 Windows® Server 2008 Hyper-V ロールと Windows Server 2008 フェールオーバー クラスタリング機能を組み合わせて使用することで、仮想化サーバー コンピューティング環境における高可用性を確保できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で使用される BizTalk Server コンピューターと SQL Server コンピューターは、Hyper-V の仮想化環境にインストールすることができます。その後、フェールオーバー クラスタリングを使用して高可用性を実現できます。 Hyper-V でゲスト オペレーティング システムを実行するのに伴いシステム リソース コストが発生するため、このようなソリューションを実稼働環境に展開する前に、全体のパフォーマンス テストを実行することをお勧めします。 詳細については、HYPER-V とフェールオーバー クラスタ リングを共に使用して仮想マシンの高可用性を実現するを参照してください「HYPER-V ステップ バイ ステップ ガイド:: HYPER-V とフェールオーバー クラスタ リング」 [http://go.microsoft.com/fwlink/?LinkID=129113](http://go.microsoft.com/fwlink/?LinkID=129113)です。 展開の詳細については、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V の仮想化環境でダウンロードできる BizTalk Server の HYPER-V ガイドを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=189706](http://go.microsoft.com/fwlink/?LinkId=189706)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md)   
 [BizTalk Server データベースの高可用性を実現します。](../core/providing-high-availability-for-biztalk-server-databases.md)   
 [エンタープライズ シングル サインオンの高可用性](../core/high-availability-for-enterprise-single-sign-on.md)