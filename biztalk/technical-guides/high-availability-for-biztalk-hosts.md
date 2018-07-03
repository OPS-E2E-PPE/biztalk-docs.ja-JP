---
title: BizTalk ホストの高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3153f7f7-7e82-4b0c-9b48-e9f871de285d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 959160bdf8e4e81715c77946663a9e4fc70fb077
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978667"
---
# <a name="high-availability-for-biztalk-hosts"></a>BizTalk ホストの高可用性
BizTalk Server は、受信メッセージを送信して、物理的には、オーケストレーションの処理などの機能の特定の領域を実行するホストが論理を戦略的に割り当てることができますので、高可用性をアドレス指定の柔軟性を提供します。複数のサーバーに配置されます。  
  
 内の論理コンテナーされた BizTalk ホストは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]収容でき、グループ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターなどの項目の送信ハンドラー (パイプラインを含む)、受信場所、オーケストレーションします。 通常は、拡張性の観点から似た特性を持つアイテムを特定のホストにグループ化します。  
  
 ホストを作成した後は、物理的にデプロイできます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト インスタンスとコンピューター。 指定したホスト インスタンスが、BTSNTSvc.exe (または 64 ビット ホスト インスタンスの BTSNTSvc64.exe) Windows サービスとして実行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。 各ホストでは、特定の 1 つだけのインスタンスがあることができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。 ただし、1 つ以上の特定のホストのインスタンスを設定できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]して、コンピューターは、特定のさまざまなホストのインスタンスを配置できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。  
  
 BizTalk ホスト内に含まれる項目は、次の関数を実行できます。  
  
- **受信**します。 受信場所から取得された後のメッセージに対して初期処理を実行します。 ホストには、(パイプライン) を持つ受信場所などの受信側の項目が含まれている場合、メッセージのデコードや復号化は、ホスト内のパイプラインで発生します。  
  
- **送信**します。 送信ポートに送られる前のメッセージに対して最終処理を実行します。 ホストには、送信ポートなどの送信元の項目が含まれている場合は、ホスト内のパイプラインでメッセージの署名と暗号化が発生します。  
  
- **処理**します。 これらの項目は、オーケストレーションでの指示に基づくメッセージを処理します。  
  
  1 つの BizTalk ホストに、メッセージの受信、送信、および処理の機能をすべて割り当てることもできます。 管理とスケーラビリティが容易に、各関数の指定された別のホストを作成することをお勧めします。 具体的には、処理および受信/送信操作は、さまざまなホストを使用することをお勧めします。  
  
  たとえば、1 つのメッセージを受け取って、オーケストレーションを実行し、10 個のメッセージを送信する場合、送信には受信と比べて 10 倍のトラフィックが発生するため、受信機能と送信機能は 2 つのホストに分ける必要があります。 1 つのメッセージを受信し、オーケストレーションを実行して、1 つのメッセージを送信する場合は、3 つの機能を 1 つの作業単位と捉え、単一のホストとしてグループ化することができます。 また、管理コストは高くなりますが、3 つの機能を別々のホストに分ければ、パフォーマンスと柔軟性を高めることができます。  
  
  BizTalk ホストは、2 つの型の 1 つ*インプロセス*または*Isolated*します。 内のインプロセス ホストの実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム プロセス (BTSNTSvc.exe または BTSNTSvc64.exe) と分離ホスト実行しないでください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム プロセス。 分離ホストは、分離受信アダプターの受信側でのみ使用します。 次の表は、2 種類のホストに割り当てることのできる機能をまとめたものです。  
  
|ホストの種類|論理コンテナーに割り当てることのできる機能|  
|---------------|---------------------------|  
|インプロセス|オーケストレーション<br />のアダプター送信ハンドラー<br />・ インプロセス アダプターの受信ハンドラー|  
|分離されます。|HTTP、SOAP の受信ハンドラー<br />-その他の分離アダプターの受信ハンドラー|  
  
 BizTalk ホストとホスト インスタンスの管理に関する詳細については、次を参照してください。 [BizTalk ホストの管理およびホスト インスタンス](http://go.microsoft.com/fwlink/?LinkID=154191)(http://go.microsoft.com/fwlink/?LinkID=154191) BizTalk Server のヘルプ。  
  
 BizTalk ホストの高可用性を実現するには、2 つ以上のホスト インスタンスを環境内の各ホスト (の 2 つ以上のコンピューター) が必要です。 1 つ以上のホスト インスタンスの 1 つのホスト インスタンスが使用できなくなった場合、同じホストのインスタンスを実行する他のコンピューターで、ホストがインスタンスを確認する各ホストが、問題または障害が発生したホスト インスタンスの機能を再開することで、システム全体が最小限の中断処理を続行することができます。  
  
## <a name="disadvantages-of-additional-hosts"></a>追加のホストの短所  
 追加のホスト インスタンスを作成する利点はありますも潜在的な欠点が多すぎるのホスト インスタンスが作成された場合です。 各ホスト インスタンスは、メッセージ ボックス データベースに対して追加の負荷を生成し、CPU、メモリ、およびスレッドなどのコンピューター リソースを消費する Windows サービス (BTSNTSvc.exe または BTSNTSvc64.exe) です。 これら以外には、いない多数の追加のホスト インスタンスを構成するために、次の理由があります。  
  
-   いくつかのパフォーマンス カウンターは、1 つのホストが多すぎるの粒度で報告されます。 これにより、管理者は、大量のデータをスキャンする必要がありますにとって使いやすさが影響します。 これは、管理者は全体的なビューに悪影響を及ぼします。  
  
-   各ホストでは、相当量の制限のような状況が生じるし、パフォーマンスが低下するメモリを消費します。  
  
-   ホストがポーリングを継続的に実行するアダプターを受信した場合の各ホストは、データベースにポーリング、短い間隔でパフォーマンスの低下になります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [受信ホストのスケールアウト](../technical-guides/scaling-out-receiving-hosts.md)  
  
-   [受信ホストのクラスタリング](../technical-guides/clustering-receiving-hosts.md)  
  
-   [処理ホストのスケールアウト](../technical-guides/scaling-out-processing-hosts.md)  
  
-   [送信ホストのスケールアウト](../technical-guides/scaling-out-sending-hosts.md)  
  
## <a name="see-also"></a>参照  
 [ホストとホスト インスタンスを構成します。](../technical-guides/configuring-hosts-and-host-instances.md)   
 [専用の追跡ホストの構成](../technical-guides/configuring-a-dedicated-tracking-host.md)   
 [高 Availability2 の計画](../technical-guides/planning-for-high-availability2.md)   
 [データベースの高可用性](../technical-guides/high-availability-for-databases.md)   
 [マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)