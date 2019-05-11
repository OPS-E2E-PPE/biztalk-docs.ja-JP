---
title: 高可用性 BizTalk Server 環境を作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, high availability
- architecture, databases
- databases, architecture
- performance
- hosts, multiple
- hosts, architecture
- architecture, hosts
- databases, clustering
- high availability, designing
- BizTalk Server, architecture
- installation, planning
- clustering, databases
- installation, availability
ms.assetid: 758eb3bd-a25b-4863-a4ca-d7a1635f7542
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dad0587f02d0307140e5208043eb16735bb6f03e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354169"
---
# <a name="creating-a-highly-available-biztalk-server-environment"></a>高可用性 BizTalk Server 環境を作成します。
このセクションは、Microsoft での通信とデータの高可用性を提供する方法を説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]異種システムとアプリケーションを統合するときにします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可用性データベースをスケールすることによって発行およびホストを別々 に解決できるように、データを処理するホストが分離されます。  
  
## <a name="demonstrating-high-availability"></a>高可用性の実証  
 高可用性を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用性を低下させている機能コンポーネントの復旧にかかっています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。  
  
 高可用性をデモンストレーションする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]障害を適用し、復旧で、製品の効果を測定する必要があります。 高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開は、外部アプリケーションとシステムに、エラーや障害を透明と最小限の中断で正しく機能しているすべてのサービスを続行するようにします。  
  
## <a name="designing-for-high-availability"></a>高可用性のための設計  
 設計、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高可用性を提供する展開では、アプリケーションの統合またはビジネス プロセス統合シナリオに関連する各機能コンポーネントの冗長性を実装する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 概念的には、データを処理するホストからデータを分離することでは、これらのシナリオの実装を簡素化されます。 高可用性を実現する手段[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は、複数のホスト インスタンスを実行し、クラスタ リング、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、次のようにします。  
  
- **BizTalk ホストのアーキテクチャ**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストを分離し、メッセージの受信、処理オーケストレーション、メッセージを送信するなどの主要機能の高可用性を実現する複数のホスト インスタンスを実行することができます。 これらのホストので必要ありません、クラスタ リングを追加または負荷分散メカニズム[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ワークロードを複数のコンピューターのホスト インスタンスを自動的に分散します。 ただし、HTTP および SOAP アダプターの受信ハンドラーを実行しているホストには、負荷分散メカニズムなどネットワーク負荷分散 (NLB) の高可用性を提供する必要があります。  
  
- **BizTalk Server データベースのアーキテクチャ**の高可用性、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは通常、アクティブ/パッシブのサーバー クラスター構成で構成されている 2 つ以上のデータベース コンピューターで構成されます。 これらのコンピューターでは、共通のディスク リソース (RAID5 SCSI ディスク アレイやストレージ エリア ネットワークなど) を共有し、Windows クラスタ リングを使用して、バックアップの冗長性とフォールト トレランスを提供します。  
  
> [!NOTE]
>  高可用性環境は、性質上、複数コンピューター環境です。 構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複数コンピューター環境では、ドメイン ユーザー グループとアカウントを使用する必要があります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基に構築されて[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]と用のホストを構成する前に、高可用性を備えた、これらの製品をデプロイすることを確認、Microsoft SQL Server 2008[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 次のリンクには、これらの基になる製品用の高可用性を実現するに関する情報が含まれます。  
  
- **高可用性 – Always On Technologies**、 [ http://go.microsoft.com/fwlink/?LinkId=130376](http://go.microsoft.com/fwlink/?LinkId=130376)します。  
  
   このホワイト ペーパーでは、SQL Server 2008 で利用できる高可用性機能について説明します。  
  
- **高可用性ソリューションの概要**、 [ http://go.microsoft.com/fwlink/?LinkId=130377](http://go.microsoft.com/fwlink/?LinkId=130377)します。  
  
   SQL Server 2008 のサーバーやデータベースの可用性を向上するにはいくつかの高可用性ソリューションについて説明します。  
  
- **Windows 展開サービス ステップ バイ ステップ ガイド**、 [ http://go.microsoft.com/fwlink/?LinkId=130379](http://go.microsoft.com/fwlink/?LinkId=130379)します。  
  
   Windows Server 2008、Windows 展開サービス ロールを使用する方法についてステップ バイ ステップ ガイダンスが含まれています。  
  
- **Windows Server 2003 展開キット:サーバーの導入計画**、 [ http://go.microsoft.com/fwlink/?LinkId=24433](http://go.microsoft.com/fwlink/?LinkId=24433)します。  
  
   このドキュメントでは、サーバーの記憶域、および情報を設計し、ファイル サーバー、プリント サーバー、および中規模および大規模組織内のターミナル サーバーの配置に関する計画に関する情報を提供します。  
  
- **BizTalk Server の可用性を高める**、 [ http://go.microsoft.com/fwlink/?LinkId=130457](http://go.microsoft.com/fwlink/?LinkId=130457)します。  
  
   セクション、 [BizTalk Server 運用ガイド](http://go.microsoft.com/fwlink/?LinkId=130458)の可用性を向上させる方法について説明する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md)  
  
-   [BizTalk Server データベースの高可用性を実現します。](../core/providing-high-availability-for-biztalk-server-databases.md)  
  
## <a name="see-also"></a>参照  
 [サンプル BizTalk Server の高可用性のシナリオ](../core/sample-biztalk-server-high-availability-scenarios.md)   
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)