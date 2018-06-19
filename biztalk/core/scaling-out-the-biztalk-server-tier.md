---
title: BizTalk Server 層のスケール アウト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, planning
- scaling, load balancing
- host instances, scaling
- scaling, examples
- fault tolerance
- scaling, scaling out
- scaling, fault tolerance
- NLB system, scaling
- scaling, host instances
ms.assetid: 01d1ab20-d7a9-4d0b-a61e-65e56fe5010e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35674e89d8f8104a35718531f2a87f95e8bc67e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271970"
---
# <a name="scaling-out-the-biztalk-server-tier"></a>BizTalk Server 層のスケール アウト
BizTalk Server 層をスケール アウトするには、追加のハードウェアを既存のトポロジに追加します。 次のシナリオでは、ハードウェアを追加することをお勧めします。  
  
-   BizTalk Server がボトルネックになります。 ボトルネックは、次のいずれかの問題によって引き起こされる可能性があります。  
  
-   CPU: CPU を集中的に使用するパイプライン、マップ、またはオーケストレーションをシナリオで使用する場合に、BizTalk Server に余分な CPU ヘッドルームがない。  
  
-   メモリと I/O: 既存のコンピューターのメモリおよび I/O が上限に達した場合に、リソースを追加する方法として、別の物理的なコンピューターを追加するしかない。  
  
-   スケール アップは、非常に高コストです。 たとえば、BizTalk の CPU が最大容量に達しているシングル BizTalk Server トポロジについて考えてみます。 デュアル プロセッサをクワド プロセッサにアップグレードするよりもデュアル プロセッサを搭載したコンピューターを追加する方がコストがかからない場合は、システムをスケール アウトする必要があります。  
  
-   スケール アップは、ボトルネックを解消しません。 次のシナリオでは、スケール アップが機能しない場合があります。  
  
    -   I/O が BizTalk コンピューターの最大値に達したので、I/O を調整するために別のコンピューターが必要である。  
  
    -   メモリがオペレーティング システムの最大値に達している。 このシナリオで、システムを拡張する方法は、BizTalk コンピューターをトポロジに追加する方法だけです。  
  
 一部のシナリオでは、メッセージの受信、メッセージの送信、およびその処理を行う専用サーバーが必要になる場合があります。 専用サーバーがあれば、問題を切り離して、他のコンピューターに影響を与えることなく 1 台のコンピューターの保守を行うことが容易です。 BizTalk 層を拡張して、これらのコンピューターを追加できます。  
  
## <a name="when-you-cant-scale-out-the-biztalk-tier"></a>BizTalk 層をスケール アウトできない場合  
  
-   メッセージ ボックス データベースがボトルネックの場合。  
  
-   アダプターがボトルネックになる場合。 たとえば、SQL アダプターを使用している場合、BizTalk の受信者数を増やすと、BizTalk SQL アダプターがデータを抽出する SQL データベースでロックの競合が増えます。 このため、SQL アダプターのスケール アウトが制限されます。  
  
 次の図は、BizTalk 層のスケール アウト方法の例を示しています。  
  
 ![BTS のスケール アウト](../core/media/scaleoutbts.gif "ScaleOutBTS")  
  
 この図は、スケール アウトされた BizTalk トポロジを示しています。シングル BizTalk Server からダブル BizTalk Server に拡張されています。 シングル BizTalk Server トポロジでは、3 つのホスト インスタンスが BizTalk コンピューター リソースを共有しています。 ダブル BizTalk Server トポロジでは、送信ホストが別のサーバーに分離され、スループットが向上します。  
  
## <a name="considerations-when-scaling-out-the-biztalk-tier"></a>BizTalk 層をスケール アウトする際の注意  
 別の BizTalk Server コンピューターを追加する前に、次の質問を考慮する必要があります。  
  
#### <a name="how-do-i-configure-the-system-for-load-balancing-and-fault-tolerance-when-i-scale-out-the-biztalk-tier"></a>BizTalk 層をスケール アウトする際、負荷分散およびフォールト トレランスを考慮するとシステムをどのように構成すればよいか  
 負荷分散およびフォールト トレランスを使用するかどうかは、シナリオで使用されているアダプターによって異なります。 SOAP アダプターおよび HTTP アダプターを使用する場合、NLB を使用することをお勧めします。 詳細については、NLB のドキュメントを参照してください。  
  
#### <a name="how-do-i-refactor-the-host-instances"></a>ホスト インスタンスをリファクタリングするにはどうすればよいか  
 BizTalk 層をスケール アウトする際にホスト インスタンスをリファクタリングする方法を規定している規則はありません。 ホスト インスタンスをファクタリングする時期は、シナリオの複雑さによって異なります。 ホスト インスタンスをファクタリングする方法の例をいくつか次に示します。  
  
##### <a name="scenario-1"></a>シナリオ 1  
 シングル BizTalk Server 構成で、受信用と送信用のホスト インスタンスが同じコンピューター上にあります。  
  
 CPU にボトルネックがあると仮定します。 スケール アウトするために別の同等の BizTalk コンピューターをグループに追加する場合、ホスト インスタンスをファクタリングする方法は 2 つあります。  
  
 この問題の 2 つの解決方法を次に示します。  
  
-   **解決策 1**: このシナリオでファクタリングの最も簡単な方法は、ファクタリングするホスト インスタンスの最初のコンピューターから 2 つ目のコンピューターに複製します。 したがって、2 番目のコンピューターは、機能性の面で 1 番目のコンピューターと完全に同等になります。また、受信ホストおよび送信ホストの両方を使用できます。 他のボトルネックがないと仮定した場合、CPU リソースが 2 倍になるため、スケール ファクターは 2 となります。  
  
-   **解決策 2**: ホスト インスタンスをファクタリングする別の方法は、受信を分離し、別のコンピューターに関数を送信します。 したがって、1 つの BizTalk Server を受信用に使用し、他の BizTalk Server を送信用に使用します。  
  
 **解決方法 1 と 2 のソリューションの比較**  
  
 解決方法 1 のホスト インスタンス数は、シングル BTS 構成の 2 倍になります。 つまり、SQL Server 上のロックの競合が増加することを示しています。 ロックの競合がどれだけ増えるかによって、スケール ファクターが決まります。 ロックの競合がボトルネックとなる制限の範囲内の場合、スケール ファクターは 2 になります。  
  
 解決方法 2 の場合は、SQL server のロックの競合は解決方法 1 よりも少なくなるために、2 つのホスト インスタンスがあること。 ただし、スケール ファクターが、受信の複雑さに完全に依存し、送信ホスト インスタンス。 解決方法 2 での次のような事例を考えてみます。  
  
 受信ホスト インスタンスと送信ホスト インスタンスに同じ負荷がかかり、シングル BizTalk Server トポロジでそれぞれが CPU の 50% を使用していると仮定します。 ダブル BizTalk Server トポロジでは、送信ホスト インスタンスを別のコンピューターに移動するため、受信と送信の両方でリソースを 2 倍消費します。 このため、他のボトルネックがないと仮定した場合、スケール ファクターは 2 になります。 ホスト インスタンスが 2 つだけでロックの競合が少ないため、この事例では解決方法 1 よりも適しています。  
  
 受信よりも送信に多くの負荷がかかり、シングル BizTalk Server トポロジで 80% の CPU リソースを消費していると仮定します。 送信ホスト インスタンスを別のコンピューターに移動しても、使用できる CPU リソースは 20% しか増えません。このため、スケール ファクターの最大値は、1.2 になります。 さらに、受信ホスト インスタンスのコンピューターは、CPU リソースを 20 ～ 30% しか使用しません。このため、スケールアウトの利点はさらに少なくなります。  
  
 4 つの BizTalk Server のある次の図を見てください。 各コンピューターは、受信と送信の役割を果たし、各種類 (受信と送信) の 4 つのホスト インスタンスが提供されています。  
  
 ![Re &#45; ホスト インスタンスをファクタリング](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")  
  
 このトポロジは、最適ではありません。 また、シナリオの複雑さに応じて、他のファクタリングの配置をテストする必要があります。 例:  
  
-   受信用と送信用にそれぞれ 2 台のコンピューターを使用します。 これによって、受信と送信で同じ負荷がかかった場合に、最適な拡張を行うことができます。  
  
-   送信よりも受信に負荷がかかっている場合、受信用に 3 台のコンピューター、送信用に 1 台のコンピューターを使用します。  
  
-   受信よりも送信に負荷がかかっている場合、受信用に 1 台のコンピューター、送信用に 3 台のコンピューターを使用します。  
  
 すべてのシナリオにおいて、メッセージ ボックス データベースの競合を減らすと共にコンピューター リソースを最大限に利用するため、各ホストのホスト インスタンスの数を最小限にすることをお勧めします。 最適なファクタリングの配置は、シナリオの複雑さとボトルネックの種類によって異なります。 配置を決める前にファクタリングを必ずテストしてください。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md)   
 [SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md)   
 [SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md)   
 [スケール アウト受信ホスト](../core/scaled-out-receiving-hosts.md)   
 [スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md)   
 [スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md)   
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [スケール アウト データベース](../core/scaled-out-databases.md)   
 [BizTalk Server データベースをクラスタ リング](../core/clustering-the-biztalk-server-databases1.md)