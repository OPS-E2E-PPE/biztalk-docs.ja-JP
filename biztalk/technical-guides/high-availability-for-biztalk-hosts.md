---
title: BizTalk ホストの高可用性 |Microsoft ドキュメント
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
ms.openlocfilehash: 29636a63f7847017b233275ee3dd7c2c389c43be
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009995"
---
# <a name="high-availability-for-biztalk-hosts"></a>BizTalk ホストの高可用性
BizTalk Server は、非常に柔軟に特定の受信とメッセージを送信することができる物理的にオーケストレーション処理などの機能領域を実行する論理的なホストを戦略的に割り当てることができますので、高可用性をアドレス指定複数サーバーに配置します。  
  
 BizTalk ホスト内の論理コンテナーとは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]収容でき、グループ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターなどの項目の送信ハンドラー (パイプラインを含む)、受信場所、オーケストレーションです。 通常は、拡張性の観点から似た特性を持つアイテムを特定のホストにグループ化します。  
  
 ホストを作成した後は、物理的に展開できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト インスタンスとコンピューター。 ホスト インスタンスが、指定の Windows サービスは、BTSNTSvc.exe (または 64 ビット ホスト インスタンスの BTSNTSvc64.exe) として実行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。 各ホストの場合は、特定のインスタンス 1 つだけを持つことができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。 ただし、1 つ以上の特定のホストのインスタンスを持つことができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]して、コンピューターは、特定のさまざまなホストのインスタンスを持つことができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。  
  
 BizTalk ホストに含まれているアイテムには、次の関数を実行できます。  
  
-   **受信**です。 受信場所から取得された後のメッセージに対して初期処理を実行します。 ホストには、受信場所 (パイプライン) を持つように、受信側アイテムが含まれている場合は、ホスト内のパイプラインでメッセージのデコードや復号化が発生します。  
  
-   **送信**です。 送信ポートに送られる前のメッセージに対して最終処理を実行します。 ホストには、送信ポートなどの送信元の項目が含まれている場合、メッセージの署名と暗号化は、ホスト内のパイプラインで発生します。  
  
-   **処理**です。 これらの項目は、オーケストレーションの命令に基づいてメッセージを処理します。  
  
 1 つの BizTalk ホストに、メッセージの受信、送信、および処理の機能をすべて割り当てることもできます。 簡単な管理とスケーラビリティは、各関数の指定した別のホストを作成することをお勧めします。 具体的には、処理との受信/送信操作には、別のホストを使用することをお勧めします。  
  
 たとえば、1 つのメッセージを受け取って、オーケストレーションを実行し、10 個のメッセージを送信する場合、送信には受信と比べて 10 倍のトラフィックが発生するため、受信機能と送信機能は 2 つのホストに分ける必要があります。 1 つのメッセージを受信し、オーケストレーションを実行して、1 つのメッセージを送信する場合は、3 つの機能を 1 つの作業単位と捉え、単一のホストとしてグループ化することができます。 また、管理コストは高くなりますが、3 つの機能を別々のホストに分ければ、パフォーマンスと柔軟性を高めることができます。  
  
 BizTalk ホストは、2 つの型の 1 つ*インプロセス*または*Isolated*です。 インプロセス ホストでは、内の実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム プロセス (BTSNTSvc.exe または BTSNTSvc64.exe) と分離ホストで実行しない、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム プロセスです。 分離ホストは、分離受信アダプターの受信側でのみ使用されます。 次の表は、2 種類のホストに割り当てることのできる機能をまとめたものです。  
  
|ホストの種類|論理コンテナーに割り当てることのできる機能|  
|---------------|---------------------------|  
|インプロセス|オーケストレーション<br />のアダプター送信ハンドラー<br />・ インプロセス アダプターの受信ハンドラー|  
|分離されます。|HTTP、SOAP の受信ハンドラー<br />-その他の分離アダプターの受信ハンドラー|  
  
 BizTalk ホストとホスト インスタンスの管理に関する詳細については、次を参照してください。[を管理する BizTalk ホストとホスト インスタンス](http://go.microsoft.com/fwlink/?LinkID=154191)(http://go.microsoft.com/fwlink/?LinkID=154191)、BizTalk Server のヘルプ。  
  
 BizTalk ホストの高可用性を実現するには、2 つ以上のホスト インスタンスを環境内 (2 つ以上のコンピュータ) の各ホストが必要です。 1 つ以上のホスト インスタンスを確認する 1 つのホスト インスタンスが使用できなくなった場合、ホスト インスタンスの同じホストのインスタンスを実行している他のコンピューター上の各ホストは、問題や障害が発生したホスト インスタンスの機能を再開できますを用意することによって、システム全体が中断を最小限を実行することを続行することができます。  
  
## <a name="disadvantages-of-additional-hosts"></a>他のホストの短所  
 追加のホスト インスタンスを作成する利点があるときに欠点がありますも潜在的な多数のホスト インスタンスが作成される場合。 各ホスト インスタンスは、メッセージ ボックス データベースに対して追加の負荷を生成し、CPU、メモリ、スレッドなど、コンピューター リソースを消費する Windows サービス (BTSNTSvc.exe または BTSNTSvc64.exe) です。 これら以外には、多数の追加のホスト インスタンスが未構成の次の理由があります。  
  
-   いくつかのパフォーマンス カウンターは、ホストごとに 1 が多すぎる粒度で報告されます。 これは、使いやすさが大量のデータの間を移動する必要がありますが、管理者のために影響します。 これは、管理者は全体的なビューに悪影響を及ぼします。  
  
-   各ホストでは、相当量の制限の状態になる可能性があり、パフォーマンスが低下するメモリを消費します。  
  
-   場合は、ホストがポーリングを継続的に実行するアダプターを受けるが、各ホストはポーリング、データベース、短い間隔では、パフォーマンスが低下します。  
  
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