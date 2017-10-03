---
title: "高可用性の BizTalk Server 環境を作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "54"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87044102248d371ea19ed07d676a0e7a0861296e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-highly-available-biztalk-server-environment"></a>高可用性 BizTalk Server 環境の構築
このセクションのデータと Microsoft での通信に高可用性を実現する方法について説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]多種多様なシステムおよびアプリケーションを統合するときにします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用性データベースをスケーリングして発行およびホストを別々 に解決できるように、データを処理するホストからデータを分離します。  
  
## <a name="demonstrating-high-availability"></a>高可用性の実証  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の高可用性は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 展開の可用性を低下させている機能コンポーネントの復旧にかかっています。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の高可用性を実証するには、障害を想定して製品の復旧能力を評価する必要があります。 高い可用性を備えた [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境の条件は、そのエラーや障害が外部のアプリケーションやシステムに影響を与えることなく、混乱を最小限に抑えながら、すべてのサービスが正常な機能を維持できることです。  
  
## <a name="designing-for-high-availability"></a>高可用性を実現するための設計  
 設計、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション統合またはビジネス プロセス統合シナリオに関連する各機能コンポーネントの冗長性を実装する高可用性を提供する展開が含まれます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]概念的には、データを処理するホストからデータを分離することにより、これらのシナリオの実装を簡素化されます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の高可用性を実現する手段として、次のように、複数のホスト インスタンスの実行や、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースのクラスター化があります。  
  
-   **BizTalk ホストのアーキテクチャ**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストを分離し、メッセージの受信、オーケストレーション、処理、およびメッセージを送信するなどの主要機能のための高可用性を実現する複数のホスト インスタンスを実行することができます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではホスト インスタンスを通じて複数のコンピューターに自動的に負荷が分散されるため、これらのホストにクラスタリングを追加したり、負荷分散メカニズムを適用する必要はありません。 ただし、HTTP アダプターおよび SOAP アダプターの受信ハンドラーを実行するホストに高可用性を確保するためには、ネットワーク負荷分散 (NLB) などの負荷分散メカニズムが必要となります。  
  
-   **BizTalk Server データベースのアーキテクチャ**の高可用性、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アクティブ/パッシブのサーバー クラスター構成で構成されている 2 つ以上のデータベース コンピューターのデータベースが通常で構成されます。 複数のコンピューターが同じディスク リソース (RAID5 SCSI ディスク アレイやストレージ エリア ネットワークなど) を共有し、Windows クラスタリングを通じてバックアップの冗長性とフォールト トレランスを提供します。  
  
> [!NOTE]
>  高い可用性を備えた環境とは、本質的に複数のコンピューターから成る環境です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を複数コンピューター環境で構成する場合は、ドメイン ユーザー グループとアカウントを使用する必要があります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]、および Microsoft SQL Server 2008 を基盤としているので、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用のホストを構成する前に、高可用性を実現しながらこれらの製品を展開する必要があります。 こうした基盤となる製品の高可用性を実現する方法については、次のリンクを参照してください。  
  
-   **高可用性 – Always On Technologies**」には、 [http://go.microsoft.com/fwlink/?LinkId=130376](http://go.microsoft.com/fwlink/?LinkId=130376)です。  
  
     このホワイトペーパーでは、SQL Server 2008 で使用できる高可用性機能について説明しています。  
  
-   **高可用性ソリューションの概要**」には、 [http://go.microsoft.com/fwlink/?LinkId=130377](http://go.microsoft.com/fwlink/?LinkId=130377)です。  
  
     サーバーまたはデータベースの可用性を向上させる SQL Server 2008 の高可用性ソリューションについて説明します。  
  
-   **Windows 展開サービス ステップ バイ ステップ ガイド**」には、 [http://go.microsoft.com/fwlink/?LinkId=130379](http://go.microsoft.com/fwlink/?LinkId=130379)です。  
  
     Windows Server 2008 で Windows 展開サービス ロールを使用する方法についてのステップ バイ ステップ ガイドを含みます。  
  
-   **Windows Server 2003 導入ガイド: サーバーの展開を計画する**」には、 [http://go.microsoft.com/fwlink/?LinkId=24433](http://go.microsoft.com/fwlink/?LinkId=24433)です。  
  
     このドキュメントでは、サーバー ストレージの導入計画のほか、中規模から大規模な組織におけるファイル サーバー、プリント サーバー、およびターミナル サーバーの設計と導入について説明しています。  
  
-   **BizTalk Server の可用性を高める**」には、 [http://go.microsoft.com/fwlink/?LinkId=130457](http://go.microsoft.com/fwlink/?LinkId=130457)です。  
  
     セクションで、 [BizTalk Server 運用ガイド](http://go.microsoft.com/fwlink/?LinkId=130458)の可用性を向上させる方法を説明する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk ホストの高可用性](../core/providing-high-availability-for-biztalk-hosts.md)  
  
-   [BizTalk Server データベースの高可用性を実現します。](../core/providing-high-availability-for-biztalk-server-databases.md)  
  
## <a name="see-also"></a>参照  
 [サンプル BizTalk Server の高可用性のシナリオ](../core/sample-biztalk-server-high-availability-scenarios.md)   
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)