---
title: BizTalk Server の可用性の向上 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72d9ce5e-d775-4f8e-b1a4-bf3c7c05f571
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6de74c7efb9aa4f900d555c265318bb17118082
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023704"
---
# <a name="increasing-availability-for-biztalk-server"></a>BizTalk Server の可用性の向上
このセクションの可用性を向上させる方法を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。  
  
## <a name="strategies-for-increasing-availability"></a>可用性を高めるための戦略  
 可用性を高めるための戦略を以下に示します。  
  
- **Windows Server 2003 サーバー クラスターまたは Windows Server 2008 フェールオーバー クラスタ リングを使用して高可用性を提供する**します。 サーバーまたはフェールオーバー クラスターは、重要なアプリケーションとリソースがクライアントで使用できる維持するために 1 つのシステムとして連携して、ノードと呼ばれる、独立したコンピューターのシステムのグループです。 ノードの 1 つの障害やメンテナンスのダウンタイムの要件の結果として利用できなくなると、すぐに別のノードがサービス (フェールオーバーと呼ばれるプロセス) の提供を開始します。  
  
  - サーバーまたはフェールオーバー クラスターは通常そのハウスの SQL Server を実行するコンピューターの推奨、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
  - サーバー クラスターは、特定の BizTalk アダプターの高可用性を実現する必要があります。  
  
  - サーバー クラスターは通常、エンタープライズ シングル サインオン マスター シークレット サーバーをお勧めします。  
  
- **負荷分散のフォームを使用して高可用性を提供する**します。  
  
  - ネットワーク負荷分散 (NLB)。 NLB は、ホストが失敗したかオフラインの場合、NLB クラスター ホストを操作への着信ネットワーク トラフィックのリダイレクトにより、高可用性を実現します。 サーバーのクラスターとは異なり、NLB は、特殊なハードウェアを必要ありません。  
  
  - BizTalk ホストの負荷分散します。 実行している複数のサーバーを追加することで、BizTalk ホストの BizTalk ホストの負荷分散が提供されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループと、これらのサーバーで実行するインプロセス ホストの複数のインスタンスを構成します。 これにより、そのホストで構成されているサービスとアイテムの実行がホストの複数のインスタンスに分散されて、可用性とスケーラビリティが向上します。  
  
    > [!NOTE]  
    >  ホストの負荷分散機能は、インプロセス ホストでのみ使用できます。  
  
  - SQL Server のディスク、SAN を使用して、または複数のメッセージ ボックス データベースを追加することで負荷分散を提供しています。  
  
- 提供するための戦略**可用性を向上させる**します。 これらの戦略を可用性を向上することも、管理者が実行時に 1 つまたは複数のアクションを実行することが必要です。 そのためこれらの戦略が通常と考えられるの高可用性ではなく可用性の向上を提供します。  
  
  - 可用性を使用して増やす[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布とディザスター リカバリー。  
  
  - 適切な監視とメンテナンス戦略の実装を通じて可用性が向上します。  
  
## <a name="difference-between-clustering-and-disaster-recovery"></a>クラスタ リングの違いとディザスター リカバリー  
 クラスターとディザスター リカバリー可用性を向上させる、それらの主な違いはクラスターは、ディザスター リカバリーよりもはるかに高速の復旧時間を通常提供します。 したがって、サーバーまたはフェールオーバー クラスターでソリューションをビルドまたは負荷分散はよく考えることだけで可用性を実現するのではなく高可用性を提供します。  
  
 ディザスター リカバリーは、失敗したシステムの操作を再開することができますが、手動プロセスでは、通常と高可用性の実装よりも多くの復旧時間が必要です。 そのため、可用性がない高可用性、災害復旧の実装を提供します。 サーバーまたはフェールオーバー クラスターと、負荷分散による高可用性と、運用環境でのディザスター リカバリーによる可用性の両方を使用する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [高可用性の実現](../technical-guides/providing-high-availability.md)  
  
-   [ディザスター リカバリー](../technical-guides/disaster-recovery.md)  
  
## <a name="see-also"></a>参照  
 [チェックリスト: フォールト トレランスまたは負荷分散と高可用性を実現します。](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)   
 [チェックリスト: ディザスター リカバリーによる可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)