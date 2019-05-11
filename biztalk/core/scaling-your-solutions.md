---
title: ソリューションの拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, scaling
- scaling, scaling out
- scaling, performance
- scaling, about scaling
- scaling, scaling up
- scaling
ms.assetid: e2acbaa4-29d3-4c89-ac1f-c0641cfa0442
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 068bea9427ad82621307b0db41714aa2f9db49d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308688"
---
# <a name="scaling-your-solutions"></a>ソリューションの拡張
BizTalk Server アーキテクチャでは、スケーラビリティに優れたサポートを提供します。 選択した拡張パターンは、シナリオ、ハードウェア、およびスループットと待機時間要件の複雑さによって異なります。 小さいトポロジから最初に開始し、このセクションのガイドラインに基づいてスケール アップまたはスケール ダウンを試行する必要があります。  
  
## <a name="scaling-out-and-scaling-up"></a>スケール アウトとスケール アップ  
 BizTalk Server システムのスケールを 2 つの方法はあります。  
  
- スケール アウトは、追加のコンピューターを追加するプロセスです。 たとえば、BizTalk Server の CPU リソースがボトルネックになって、別のサーバーを追加することは倍精度浮動小数点と CPU リソースが 2 倍のスループットを提供することがありますに提供します。  
  
- スケール アップは、既存のコンピューターをアップグレードするプロセスです。 たとえば、BizTalk Server コンピューターを 4 プロセッサのコンピューターから 8 プロセッサにアップグレードできます。  
  
  BizTalk Server システムが 2 つの層: BizTalk Server 層とメッセージ ボックス データベースを格納する SQL Server 層。 どのようなシナリオでは、スケール アウトまたは各層のスケール アップできます。 つまり、BizTalk Server と、メッセージ ボックス データベースのスケール アウトしたり、それらの両方をスケール アップできます。  
  
  ほとんどの場合、BizTalk 層に最初に、ボトルネックになるし、これをスケール アウトしてパフォーマンスを向上させます。ある時点で、システムと使用するハードウェアの複雑さ、によってすることはできず、スケール アウト BizTalk 層もう、SQL Server 層がボトルネックになります。 次に、SQL Server の層をスケール アップし、次にメッセージ ボックス データベースを追加してスケール アウト。  
  
> [!NOTE]
>  新しいメッセージ ボックス データベースもここで別のサーバーとは限りません。 単一の SQL server では、複数のメッセージ ボックス データベースを持つことができます。 また、データベースが異なるコンピューター上にある場合、複数のメッセージ ボックス データベースは、DTC コストとネットワーク ホップが発生します。  
  
 理論上は、SQL Server 層スケール アウトできます無期限にマスター メッセージ ボックス データベースが飽和状態にならない限り、します。  
  
 このセクションでは、これらの拡張パターンについて詳しく説明します。 これらはまた、各パターンをスケーリングする方法およびシステムのスケールを使用できるのパターンでは不要になったを確認する方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [スケーラビリティについて](../core/what-is-scalability.md)  
  
-   [BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md)  
  
-   [BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md)  
  
-   [SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md)  
  
-   [SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md)  
  
## <a name="see-also"></a>参照  
 [受信ホスト スケール アウト](../core/scaled-out-receiving-hosts.md)   
 [スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md)   
 [スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md)   
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [スケール アウト データベース](../core/scaled-out-databases.md)   
 [BizTalk Server データベースのクラスタリング](../core/clustering-the-biztalk-server-databases1.md)