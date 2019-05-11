---
title: 高可用性とディザスター リカバリーの計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7efba36-6d9c-4ae0-a4f5-893eb5d62a05
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d68ae1c38802c0314844691a34ef4e7220ca8c54
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400716"
---
# <a name="planning-for-high-availability-and-disaster-recovery"></a>高可用性とディザスター リカバリーの計画
ソリューションを使用して開発[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を最大限の可用性を必要とするエンタープライズ レベルのアプリケーションはミッション クリティカルなことがよくあります。 これらのソリューションが運用環境に配置されると、数千ドル 1 秒あたりのダウンタイムに関連するコストを測定できます。 このため、高可用性とディザスター リカバリー機能で利用できるを最大化する特定の戦略を採用する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サポートするために必要なハードウェアとソフトウェアの依存関係を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
## <a name="hardware-considerations"></a>ハードウェアについての注意事項  
 高可用性を確保、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境、ハードウェアを計画するときに、次を検討してください。  
  
- グループ内の BizTalk サーバー間での BizTalk ホストの複数のインスタンスを実行している対応するために、BizTalk グループ内 (少なくとも 2 つ) の複数の BizTalk server を実行する方法を計画します。 これは、ホスト インスタンスで実行されているプロセスの負荷分散およびフォールト トレランスを可能になります。  
  
- 家に記憶域エリア ネットワーク (SAN) の実装を検討、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 SAN ディスクは、RAID を使用して構成する必要があります最高のパフォーマンスと高可用性を実現可能であれば、1 + 0 (ミラー セットのストライプ) トポロジ。 家に SAN の使用の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください、 [BizTalk Server データベースの最適化に関するホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkID=101578) (<http://go.microsoft.com/fwlink/?LinkID=101578>)。  
  
- 格納するための複数の SQL server のインストールの計画、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 複数の SQL server に必要な[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)](推奨) クラスタ リングや、特定のハウジング[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で別個の物理データベース[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス (もお勧めします)。  
  
- 仮想環境を使用して、ハードウェアのコストを制御することを検討してください。 Microsoft では、Microsoft Virtual Server 2005 R2、Windows Server 2008 HYPER-V、および Microsoft HYPER-V Server 2008 などの仮想化製品の範囲を提供します。 使用に関する推奨事項の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仮想環境で、次を参照してください。 [BizTalk Server 2009 Hyper-v ガイド](http://go.microsoft.com/fwlink/?LinkId=151834)(<http://go.microsoft.com/fwlink/?LinkId=151834>)。  
  
- 組織のインターネット関連のサービスを提供する境界ネットワークのドメインに 1 つまたは複数の Windows サーバーをインストールする方法を計画します。 ネットワーク負荷分散 (NLB) ソリューションを使用して、境界ネットワークのドメインで複数の Windows サーバーを構成します。 詳細については、次を参照してください。[ネットワーク負荷分散展開ガイド](http://go.microsoft.com/fwlink/?LinkId=153139)(http://go.microsoft.com/fwlink/?LinkId=153139)します。  
  
   境界ネットワーク内のサーバーのインストールの詳細については、次を参照してください。[構成 Your ドメインときに公開するトランスポートには、インターネットに](../technical-guides/planning-for-sending-and-receiving.md#BKMK_InternetTrans)します。  
  
  > [!NOTE]  
  >  境界ネットワークは、DMZ、非武装地帯、およびスクリーン サブネットとも呼ばれます。  
  
## <a name="software-considerations"></a>ソフトウェアの考慮事項  
 高可用性を確保、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、ソフトウェアを計画するときに、次を検討してください。  
  
- Enterprise Edition でに対する投資を検討[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk ホストのクラスタ リングを有利または複数のメッセージ ボックス データベースを実行している有利シナリオに対応するためにします。 通常、いる BizTalk ホストをクラスター化する必要があります、唯一の理由は、特定の BizTalk アダプターの高可用性を実現することです。 高可用性を実現するホスト クラスタ リングを使用して BizTalk アダプターの詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](http://go.microsoft.com/fwlink/?LinkID=151284)(<http://go.microsoft.com/fwlink/?LinkID=151284>)。  
  
- 家に Windows Server クラスターの実装の計画、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースと、エンタープライズ シングル サインオン マスター シークレット サーバーです。 クラスターの高可用性を実現する Windows Server を使用の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースと、エンタープライズ シングル サインオン マスター シークレット サーバーを参照してください[データベースの高可用性](../technical-guides/high-availability-for-databases.md)と[。マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)します。  
  
## <a name="high-availability-vs-disaster-recovery"></a>高可用性とします。災害復旧  
 可用性を高めるための 2 つの規定されたメソッドがある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境: フォールト トレランスや負荷分散、またはディザスター リカバリーを使用して可用性の向上を提供することを使用して高可用性を提供します。 各メソッドでは、可用性が向上、中にそれらの主な違いは、そのフォールト トレランスや、負荷分散を通常は、ディザスター リカバリーよりもはるかに高速の復旧時間を提供します。 フォールト トレランスおよび負荷分散を提供**高可用性**ディザスター リカバリーを提供しますが、**可用性を向上させる**します。 ディザスター リカバリーを実装する方法の詳細については、次を参照してください。[チェックリスト。ディザスター リカバリーによる可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)と[ディザスター リカバリー](../technical-guides/disaster-recovery.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の可用性の向上](../technical-guides/increasing-availability-for-biztalk-server.md)   
 [チェックリスト:フォールト トレランスまたは負荷分散と高可用性を実現します。](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)