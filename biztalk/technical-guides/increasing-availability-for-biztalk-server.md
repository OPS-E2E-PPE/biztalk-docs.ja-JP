---
title: BizTalk Server の可用性を高める |Microsoft ドキュメント
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
ms.openlocfilehash: aa48d7dada00ebadf089834f5025f3fdfdf25070
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298002"
---
# <a name="increasing-availability-for-biztalk-server"></a>BizTalk Server の可用性の向上
このセクションの可用性を向上させる方法を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。  
  
## <a name="strategies-for-increasing-availability"></a>可用性を高めるための戦略  
 可用性を高めるための戦略を以下に示します。  
  
-   **Windows Server 2003 サーバー クラスターまたは Windows Server 2008 フェールオーバー クラスタ リングを使用して高可用性を実現して**です。 サーバーまたはフェールオーバー クラスターとは、クリティカルなアプリケーションとリソースがあるクライアントが使用できることを保証する単一のシステムとして連携して機能のノードと呼ばれる独立したコンピューター システムのグループです。 障害やメンテナンスのダウンタイムの要件の結果として使用できなくなったノードのいずれかになると、すぐに別のノードがサービス (フェールオーバーと呼ばれるプロセス) の提供を開始します。  
  
    -   サーバーまたはフェールオーバー クラスターはそのハウスの SQL Server を実行しているコンピューターのことをお勧め通常、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
    -   サーバー クラスターは、特定の BizTalk アダプターの高可用性を実現する必要があります。  
  
    -   サーバー クラスターは通常、エンタープライズ シングル サインオン マスター シークレット サーバーをお勧めします。  
  
-   **負荷分散のフォームを使用して高可用性を提供する**です。  
  
    -   ネットワークの負荷分散 (NLB)。 NLB は、ホストが失敗したかオフラインの場合、NLB クラスターのホストを使用する受信ネットワーク トラフィックをリダイレクトすることで高可用性を提供します。 サーバー クラスターとは異なり NLB では特殊なハードウェアは必要ありません。  
  
    -   BizTalk ホストの負荷分散します。 BizTalk ホストの実行している複数のサーバーを追加することでの BizTalk ホストの負荷分散が提供される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループし、これらのサーバー上で実行するインプロセス ホストの複数のインスタンスを構成します。 これにより、そのホストで構成されているサービスとアイテムの実行がホストの複数のインスタンスに分散されて、可用性とスケーラビリティが向上します。  
  
        > [!NOTE]  
        >  ホストの負荷分散機能は、インプロセス ホストでのみ使用できます。  
  
    -   SQL Server のディスク、SAN を使用して、または複数のメッセージ ボックス データベースを追加することで負荷分散を提供しています。  
  
-   提供するための戦略**可用性の向上**です。 これらの戦略は、可用性の向上が、通常提供も、管理者が実行時に 1 つまたは複数のアクションを実行する必要があります。 したがってこれらの戦略は、通常と考えるの高可用性ではなく可用性の向上を提供します。  
  
    -   可用性を使用して増やす[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配布と障害復旧ログに記録します。  
  
    -   適切な監視と保守方法の実装を通して可用性が向上します。  
  
## <a name="difference-between-clustering-and-disaster-recovery"></a>クラスタ リングとの間の相違点と障害復旧  
 クラスターと障害復旧は、可用性を向上させる、それらの主な違いはクラスターは、災害復旧よりもはるかに高速の復旧時間を通常提供します。 したがって、サーバーまたはフェールオーバー クラスターでソリューションをビルドまたは負荷分散をよく考えるの可用性を実現するだけではなく高可用性を提供するよう。  
  
 災害復旧は、障害が発生したシステムの操作を再開することができますが、手動プロセスでは通常と高可用性実装よりも多くの復旧時間が必要です。 したがって、可用性がない高可用性、災害復旧の実装を提供します。 サーバーまたはフェールオーバー クラスターと、負荷分散による高可用性と災害復旧、実稼働でによる可用性の両方を使用する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [高可用性を提供します。](../technical-guides/providing-high-availability.md)  
  
-   [災害復旧](../technical-guides/disaster-recovery.md)  
  
## <a name="see-also"></a>参照  
 [チェックリスト: フォールト トレランスと負荷分散と高可用性を実現します。](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)   
 [チェックリスト: 災害復旧と可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)