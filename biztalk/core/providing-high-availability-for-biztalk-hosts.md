---
title: BizTalk ホストの高可用性を実現する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, MessageBox database
- planning, hosts
- hosts, high availability
- messages, routing
- deploying, high availability
- high availability, hosts
- hosts
- hosts, planning
- MessageBox database
ms.assetid: 9583b85c-7cad-4016-8065-5ca7de3f4359
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68ed85354a3f98aa8fbd08d82e5dd942e6751605
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004811"
---
# <a name="providing-high-availability-for-biztalk-hosts"></a>BizTalk ホストの高可用性
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、メッセージの送受信やオーケストレーション処理など、特定の機能領域ごとに論理的なホストを割り当てることができるため、高可用性を柔軟に実現することができます。  
  
 BizTalk ホストとは、BizTalk Server グループ内の論理的なコンテナーです。アダプター ハンドラー、受信場所 (パイプラインを含む)、オーケストレーションなど、BizTalk Server の各種アイテムが、このコンテナー内でホストされます。 通常は、拡張性の観点から似た要件を持つアイテムを特定のホストにグループ化します。 たとえば、受信場所を "受信" ホストに、送信ポートを "送信" ホストに、オーケストレーションを "処理" ホストにグループ化します。  
  
 ホスト (論理的なコンテナー) を作成した後、ホストのインスタンスが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループの物理的な.[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターで実行されるように構成できます。 ホスト インスタンスは、指定された [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上の Windows サービスとして実行されます。 特定の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上で同じホストの複数インスタンスを実行することはできませんが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループの別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターにホストのインスタンスを構成することで、特定のホストの複数インスタンスを実行できます。 また、1 台の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上で異なるホストの複数インスタンスを実行することもできます。  
  
 BizTalk ホストに格納されたアイテムは、次のような役割を果たします。  
  
- **受信**受信場所で取得された後のメッセージに対して初期処理を実行します。 受信機能 (受信場所やパイプラインなど) をつかさどるホストはセキュリティの処理境界として機能し、メッセージのデコードや復号化は、そのホスト内のパイプラインで行われます。  
  
- **送信**送信ポートに送信される前に、のメッセージに対して最終処理を実行します。 送信機能 (送信ポートやパイプラインなど) をつかさどるホストはセキュリティの処理境界として機能し、メッセージの署名や暗号化は、そのホスト内のパイプラインで行われます。  
  
- **処理**オーケストレーションの命令に基づいてメッセージを処理します。  
  
  1 つの BizTalk ホストにメッセージの受信、送信、処理を行うアイテムを入れることができますが、セキュリティの処理境界を設け、管理と拡張を容易にするためには、機能ごとに異なるホストを作成することをお勧めします。 具体的には、処理と、受信/送信操作のさまざまなホストを使用することと、信頼できる、信頼されていない項目を分離することお勧めします。  
  
  たとえば、1 つのメッセージを受け取って、オーケストレーションを実行し、10 個のメッセージを送信する場合、送信には受信と比べて 10 倍のトラフィックが発生するため、受信機能と送信機能は 2 つのホストに分ける必要があります。 1 つのメッセージを受信し、オーケストレーションを実行して、1 つのメッセージを送信する場合は、3 つの機能を 1 つの作業単位と捉え、単一のホストとしてグループ化することができます。 また、3 つの機能を別々のホストに分ければ、パフォーマンスと柔軟性を高めることができます。  
  
  BizTalk ホストは、2 つの型の 1 つ**インプロセス**または**Isolated**します。 インプロセス ホストは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のランタイム プロセス内部で実行されます。逆に、分離ホストは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のランタイム プロセス外で実行されます。 次の表は、2 種類のホストに割り当てることのできる機能をまとめたものです。  
  
|**ホストの種類**|**論理コンテナー**|  
|-------------------|-------------------------------|  
|インプロセス|オーケストレーション<br />のアダプター送信ハンドラー<br />-アダプターの受信 HTTP および SOAP 以外のハンドラー|  
|分離されます。|HTTP および SOAP の受信ハンドラー|  
  
 ホストとホスト インスタンスの詳細については、次を参照してください。 [BizTalk ホストの管理およびホスト インスタンス](../core/managing-biztalk-hosts-and-host-instances.md)します。  
  
 BizTalk ホストの高可用性を確保するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の複数コンピューター環境の各ホストに複数のホスト インスタンスを割り当てる必要があります。 各ホストに複数のホスト インスタンスを割り当てることで、1 つのホスト インスタンスで障害が発生しても、そのホストのインスタンスを実行する別のコンピューターが、問題や障害の発生したホスト インスタンスの機能を引き継ぐため、システム全体としては大きな混乱を招くことなく処理を続行できます。  
  
## <a name="message-persistence"></a>メッセージの永続性  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に関連したすべてのホストは、メッセージを BizTalk メッセージ ボックス データベースに格納します。その意味で、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] の高可用性は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に強く依存していると言えます。 たとえば、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が受信メッセージを受け取ると、受信ホストがそれをメッセージ ボックス データベースに保存して初めて、他のホストがメッセージを取得し、オーケストレーション処理を実行したり、送信したりできるようになります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソリューションにオーケストレーションを使用している場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でメッセージはビジネス プロセスを実行するホスト (処理ホスト) にルーティングされ、オーケストレーションが実行された後で、メッセージ ボックス データベースに保存されます。 その後、送信ホストが、そのメッセージをメッセージ ボックス データベースから取り出し、適切な送信アダプターを使って外部のアプリケーションに送信します。  
  
## <a name="separating-the-host-and-database-functions"></a>ホスト機能とデータベース機能の分離  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、データとそれを処理するホストが区別されています。そのため、環境の高可用性を実現するための第一歩は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で行われるホスト機能 (送信、受信、および処理) を、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] のデータベース機能から分離することです。 これらの機能を分離することにより、処理、送信、受信の各ホストと、データを保存するデータベースとを別々に拡張することができます。 ランタイム層とデータベース層の間にまったく関係がないわけではありません。通常、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターの台数を増やした場合は、追加された負荷を処理するため、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューターの台数も増やす必要があります。 ただし、データベース層と BizTalk 層に直接的な関係はありません。 両者はそれぞれ独立した層であり、別々に拡張することが可能です。  
  
 ホストとデータベースでは、高可用性を確保するための作業も異なります。 次のセクションでは、受信、送信、処理の各ホストに高可用性を実現するための作業について説明します。 データベース層の高可用性にする方法の詳細については、次を参照してください。 [BizTalk Server データベースの高可用性の実現](../core/providing-high-availability-for-biztalk-server-databases.md)します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にかかる処理の負荷が SQL Server よりも大きい環境では、複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターで、同じ SQL Server コンピューターを使用するように構成できます。 つまり、コンピューター間のリソースの不均衡をなくすように構成します。 たとえば、CPU またはメモリの使用率を比較した結果、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターのリソース使用率が高く (75% 以上)、SQL Server コンピューターのリソース使用率が低い (25% 未満) 場合、別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターを追加することにより、SQL Server コンピューターのリソース使用率を引き上げる形で、処理の負荷を分散させることが可能です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [受信ホストのスケールアウト](../core/scaled-out-receiving-hosts.md)  
  
-   [スケールアウトした処理ホスト](../core/scaled-out-processing-hosts.md)  
  
-   [スケールアウトした送信ホスト](../core/scaled-out-sending-hosts.md)  
  
-   [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースの高可用性を実現します。](../core/providing-high-availability-for-biztalk-server-databases.md)   
 [Enterprise Single Sign-On の高可用性](../core/high-availability-for-enterprise-single-sign-on.md)