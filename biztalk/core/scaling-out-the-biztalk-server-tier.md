---
title: BizTalk Server 層のスケール アウト |Microsoft Docs
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
ms.openlocfilehash: 5e04050f1d7346f06d8b0d0a7163ac28f8d538f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308966"
---
# <a name="scaling-out-the-biztalk-server-tier"></a>BizTalk Server 層のスケール アウト
BizTalk 層を拡大するには、既存のトポロジにより多くのハードウェアを追加します。 次のシナリオでは、ハードウェアを追加することをお勧めします。  
  
- BizTalk Server では、ボトルネックになります。 次の問題のいずれかでは、ボトルネックが考えられます。  
  
- CPU:シナリオでは、CPU 負荷のかかるパイプライン、マップ、またはオーケストレーションを使用する場合、BizTalk server には余分な CPU ヘッドルームはありません。  
  
- メモリと I/O:既存のコンピューターが、メモリおよび I/O が上限に達すると、リソースを追加する唯一の方法では、別の物理コンピューターを追加します。  
  
- スケール アップは、コストが高すぎます。 たとえば、BizTalk の CPU が最大能力では、1 BizTalk Server トポロジを検討してください。 デュアル プロセッサをクワド プロセッサにアップグレードする代わりに余分なデュアル プロセッサ コンピューターを追加コストは、システムのスケールよりを代わりにしてください。  
  
- スケール アップは、ボトルネックを解決できません。 スケール アップは、次のシナリオでが機能しません。  
  
  -   IO は BizTalk コンピューターの最大レベルでは別のコンピューターに、I/O を調整する必要があります。  
  
  -   メモリは、オペレーティング システムの最大レベルでです。 このシナリオでは、トポロジに追加の BizTalk コンピューターを追加する、システムを拡張するしかありません。  
  
  一部のシナリオで専用のサーバーのメッセージの受信、メッセージを送信する、およびそれらを処理する可能性があります。 専用サーバーがときは、問題を特定し、他のユーザーに影響を与えることがなく 1 台のコンピューターのメンテナンスを行うには簡単です。 これらのコンピューターを追加するには、スケーリング、BizTalk 層。  
  
## <a name="when-you-cant-scale-out-the-biztalk-tier"></a>ときに、BizTalk 層を拡大することはできません。  
  
- メッセージ ボックス データベースでは、ボトルネックです。  
  
- アダプターがボトルネックになります。 たとえば、BizTalk の受信者数を増やした後、SQL アダプターを使用する場合、BizTalk SQL アダプターがデータを抽出する SQL database でロックの競合が増加します。 これは、SQL アダプターをスケーリングする能力を制限します。  
  
  次の図は、BizTalk 層をスケールとする方法の例を示します。  
  
  ![BTS のスケール アウト](../core/media/scaleoutbts.gif "ScaleOutBTS")  
  
  この図は、スケール アウトされた BizTalk トポロジでは、2 つの BizTalk サーバーに 1 つの BizTalk server からのスケーリングを示しています。 1 つの BizTalk server トポロジで 3 つのホスト インスタンスが BizTalk コンピューター リソースを共有します。 2 つの BizTalk server トポロジより多くのスループットが実現される別のサーバーに、送信ホストが区切られています。  
  
## <a name="considerations-when-scaling-out-the-biztalk-tier"></a>スケーリング時の考慮事項は、BizTalk 層を Out します。  
 別の BizTalk Server コンピューターを追加する前に、次の質問を考慮する必要があります。  
  
#### <a name="how-do-i-configure-the-system-for-load-balancing-and-fault-tolerance-when-i-scale-out-the-biztalk-tier"></a>BizTalk 層をスケールする場合に負荷分散およびフォールト トレランスのシステムを構成する方法はありますか  
 負荷分散およびフォールト トレランスの選択は、シナリオで使用されているアダプターによって異なります。 SOAP および HTTP アダプターでは、NLB を使用することをお勧めします。 詳細については、NLB のドキュメントを参照してください。  
  
#### <a name="how-do-i-refactor-the-host-instances"></a>ホスト インスタンスをリファクタリングする方法は?  
 BizTalk 層をスケールする場合は、ホスト インスタンスをリファクタリングする方法を決定する 1 つルールがありません。 ホスト インスタンスをファクタリングする時期は、シナリオの複雑さによって異なります。 次は、ホスト インスタンスをファクタリングする方法をいくつかの例に示します。  
  
##### <a name="scenario-1"></a>シナリオ 1  
 1 つの BizTalk server 構成では、送受信を行い、ホスト インスタンスが同じコンピューター上に送信します。  
  
 CPU のボトルネックがあると仮定します。 グループに別の同等の BizTalk コンピューターを追加するスケール アウト、ホスト インスタンスをファクタリングする 2 つの方法を提供します。  
  
 この問題を解決する 2 つを次に示します。  
  
- **解決策 1**:このシナリオでファクタリングの最も簡単な方法では、ファクタリングするホスト インスタンス最初のコンピューターから 2 番目のコンピューターに複製します。 そのため、2 番目のコンピューターには、最初の正確なコピー機能性の面でどちらも持つことができますも受信および送信ホスト。 CPU リソースが 2 倍とは、その他のボトルネックがないと仮定すると、スケール ファクターは 2 を取得可能性があります。  
  
- **解決策 2**:ホスト インスタンスをファクタリングする別の方法を受信を特定し、別のコンピューターに関数を送信します。 したがって、BizTalk server の 1 つは、受信用と送信の他にです。  
  
  **解決策 1 と解決方法 2 の比較**  
  
  ソリューション 1 では、シングル BTS 構成からホスト インスタンスの数が倍になります。 これは、SQL server ロックの競合が増加することを意味します。 ロックの競合量が増えると、スケール ファクターが決まります。 ロックの競合がボトルネックとなることの制限範囲内にある場合は、スケール ファクターは 2 を表示できます。  
  
  解決方法 2 の利点は、SQL server のロックの競合の解決方法 1 より小さいをする必要がありますので、2 つのホスト インスタンスがあることです。 ただし、スケール ファクターは、受信の複雑さに完全に依存し、送信ホスト インスタンス。 解決方法 2 では、次の場合を考慮してください。  
  
  ある両方、受信および送信ホスト インスタンスが均等に負荷と 1 つの BizTalk server トポロジで、CPU の 50% を使用して、それぞれします。 2 つの BizTalk server トポロジでは、送信ホスト インスタンスを別のコンピューターに移動し、これで、受信し、送信の両方が倍精度浮動小数点のリソースを取得します。 これにより、スケール ファクターは 2、他のボトルネックがないと仮定するとが提供する必要があります。 この例は、les ロックの競合のためだけの 2 つのホスト インスタンスがあるため、解決方法 1 よりも優れています。  
  
  送信するとしますが、受信よりも方法にかかっているし、1 つの BizTalk server トポロジで 80% の CPU リソースを使用します。 別のコンピューターに送信ホスト インスタンスを移動することでは、最大のスケール ファクターは 1.2 になりますのでのみの 20% 以上の CPU リソースを行えます。 さらに、受信ホスト インスタンスを使用してコンピューターは、スケール アウトの利点ははるかに少ないために、のみの 20 ~ 30 %cpu リソースを使用しません。  
  
  次の 4 つの BizTalk サーバーがある次の図を検討してください。 各コンピューターが受信と送信、各型の 4 つのホスト インスタンスの合計を提供するには (受信し、送信) します。  
  
  ![Re&#45;ホスト インスタンスをファクタリング](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")  
  
  このトポロジは、最適できない可能性があります。 シナリオの複雑さに応じてその他のファクタリングの順列をテストすることも必要があります。 例 :  
  
- 受信するための 2 台のコンピューターと送信用に専用です。 こうと、受信し、送信は均等に負荷がかかりますが、最適な拡張します。  
  
- 専用用の 3 つの受信と送信のいずれかの受信が送信よりもかかっている場合。  
  
- 1 台のコンピューターの受信と送信の受信よりもかかってがない場合に送信するための 3 つ専用にします。  
  
  すべてのシナリオでは、メッセージ ボックス データベースでの競合の削減、同じの使用時に、コンピューター リソースを最大限ように各ホストのホスト インスタンスの数を最小限にするをお勧めします。 最適なファクタリングは、シナリオの複雑さとボトルネックの種類によって異なります。 順列を確定する前にファクタリングを必ずテストします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md)   
 [SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md)   
 [SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md)   
 [受信ホスト スケール アウト](../core/scaled-out-receiving-hosts.md)   
 [スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md)   
 [スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md)   
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [スケール アウト データベース](../core/scaled-out-databases.md)   
 [BizTalk Server データベースのクラスタリング](../core/clustering-the-biztalk-server-databases1.md)