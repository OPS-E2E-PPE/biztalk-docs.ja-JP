---
title: "高可用性と災害復旧の計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7efba36-6d9c-4ae0-a4f5-893eb5d62a05
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 742073de6f0e992e5fd0155b1939f0680fa7b3bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-high-availability-and-disaster-recovery"></a>高可用性と災害復旧の計画
開発したソリューション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最大限の可用性が必要なエンタープライズ レベルのアプリケーションはミッション クリティカルなことがよくあります。 これらのソリューションが、運用環境に配置しているときに、大量の 1 秒あたりのコストのダウンタイムに関連するコストを測定できます。 このため、高可用性と災害復旧機能で使用できるを最大化する特定の戦略を採用する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依存するソフトウェアおよびサポートするために必要なハードウェア、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
## <a name="hardware-considerations"></a>ハードウェアについての注意事項  
 高可用性を確保する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境、ハードウェアを計画するときに、次を検討してください。  
  
-   グループ内の BizTalk サーバー間での BizTalk ホストの複数のインスタンスを実行して、それに合わせて、BizTalk グループ内 (2 つ以上の) 複数の BizTalk server を実行するを計画します。 これは、ホスト インスタンスで実行されているプロセスの負荷分散およびフォールト トレランスに対応します。  
  
-   家に記憶域エリア ネットワーク (SAN) の実装の検討、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 SAN ディスクは、RAID を使用して構成する必要がありますトポロジを最高のパフォーマンスと高可用性を実現可能な場合に 1 + 0 (ストライプはミラー セット)。 家に SAN の使用の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください、 [BizTalk Server データベースの最適化のホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkID=101578) (http://go.microsoft.com/fwlink/?LinkID=101578)。  
  
-   格納するための複数の SQL server をインストールする方法を計画、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 複数の SQL server に必要な[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)](推奨) クラスタ リングや特定のハウジング[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]別個の物理データベース[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)](推奨も) のインスタンス。  
  
-   仮想環境を使用して、ハードウェアのコストを制御することを検討してください。 Microsoft では、Microsoft Virtual Server 2005 R2、Windows Server 2008 HYPER-V、および Microsoft HYPER-V Server 2008 などの仮想化製品の範囲を提供します。 使用に関する推奨事項について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仮想環境で、次を参照してください。 [BizTalk Server 2009 Hyper-v ガイド](http://go.microsoft.com/fwlink/?LinkId=151834)(http://go.microsoft.com/fwlink/?LinkId=151834)。  
  
-   組織のインターネット関連サービスを提供する境界ネットワークのドメインで 1 つまたは複数の Windows サーバーをインストールする方法を計画します。 ネットワーク負荷分散 (NLB) ソリューションを使用して境界ネットワークのドメイン内の複数の Windows サーバーを構成します。 詳細については、次を参照してください。[ネットワーク負荷分散展開ガイド](http://go.microsoft.com/fwlink/?LinkId=153139)(http://go.microsoft.com/fwlink/?LinkId=153139)。  
  
     境界ネットワーク内のサーバーのインストールの詳細については、次を参照してください。[構成、ドメインときに公開するトランスポートをインターネット](../technical-guides/planning-for-sending-and-receiving.md#BKMK_InternetTrans)です。  
  
    > [!NOTE]  
    >  境界ネットワークとは DMZ、非武装地帯およびスクリーン サブネットとも呼ばれます。  
  
## <a name="software-considerations"></a>ソフトウェアの考慮事項  
 高可用性を確保する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、ソフトウェアを計画するときに、次を検討してください。  
  
-   Enterprise Edition に投資することを検討してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]に BizTalk ホストのクラスタ リングからメリットを享受するか、実行中の複数のメッセージ ボックス データベースからすると効果的なシナリオに対応します。 通常、唯一の理由がクラスター化することは、BizTalk ホストは、特定の BizTalk アダプターの高可用性を実現することです。 詳細については、ホスト クラスタ リングを使用して BizTalk アダプターの高可用性を実現する、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](http://go.microsoft.com/fwlink/?LinkID=151284)(http://go.microsoft.com/fwlink/?LinkID=151284)。  
  
-   家に Windows Server クラスターの実装の計画、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースとエンタープライズ シングル サインオン マスター シークレット サーバーです。 高可用性を実現するクラスターの Windows Server を使用の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースと、エンタープライズ シングル サインオン マスター シークレット サーバーを参照してください[データベースの高可用性](../technical-guides/high-availability-for-databases.md)と[。マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)です。  
  
## <a name="high-availability-vs-disaster-recovery"></a>高可用性とします。災害復旧  
 2 つの指定されたメソッドの可用性を高めるため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境: フォールト トレランスおよび負荷分散、または災害復旧を使用して可用性の向上を提供することを使用して高可用性を提供します。 各メソッドでは、可用性が向上、中にそれらの主な違いは、フォールト トレランスや、負荷分散を通常は、災害復旧よりもはるかに高速の復旧時間を提供します。 フォールト トレランスおよび負荷分散を提供**高可用性**し、障害復旧は提供**可用性の向上**です。 災害復旧の実装の詳細については、次を参照してください。[チェックリスト: 可用性と災害復旧を増やす](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)と[災害復旧](../technical-guides/disaster-recovery.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の可用性の向上](../technical-guides/increasing-availability-for-biztalk-server.md)   
 [チェックリスト: フォールト トレランスと負荷分散と高可用性を実現します。](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)