---
title: "ソリューションの拡張 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, scaling
- scaling, scaling out
- scaling, performance
- scaling, about scaling
- scaling, scaling up
- scaling
ms.assetid: e2acbaa4-29d3-4c89-ac1f-c0641cfa0442
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5417e303ea8486ef5bdee8e57c66d4783fb197ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-your-solutions"></a>ソリューションの拡張
BizTalk Server アーキテクチャは、スケーラビリティに優れたサポートを提供しています。 選択する拡張パターンは、シナリオ、ハードウェア、スループット/待機時間の要件の複雑さによって異なります。 最初は小さいトポロジから始めて、このセクションのガイドラインに従ってスケールアップまたはスケールダウンを試みてください。  
  
## <a name="scaling-out-and-scaling-up"></a>スケール アウトとスケール アップ  
 BizTalk Server システムを拡張する方法は 2 とおりあります。  
  
-   スケールアウトは、別のコンピューターを追加するプロセスです。 たとえば、CPU リソースが原因で BizTalk Server にボトルネックが生じた場合、サーバーをもう 1 台追加すると CPU リソースが 2 倍になるので、2 倍のスループットを得られる可能性があります。  
  
-   スケールアップは、既存のコンピューターをアップグレードするプロセスです。 たとえば、BizTalk Server コンピューターを 4 プロセッサから 8 プロセッサにアップグレードできます。  
  
 BizTalk Server システムが 2 つの層: BizTalk Server 層と、SQL Server 層、メッセージ ボックス データベースを格納します。 いずれのシナリオでも、各層をスケール アウトまたはスケール アップすることができます。 つまり BizTalk Server とメッセージ ボックス データベースをスケール アウトしたり、両方をスケール アップすることができます。  
  
 BizTalk 層が最初にボトルネックになり、これをスケール アウトしてパフォーマンスを向上させる場合がほとんどです。ただし、使用するシステムとハードウェアの複雑さによっては、BizTalk 層をそれ以上スケール アウトできなくなり、SQL Server 層がボトルネックになります。 その場合は SQL Server 層をスケール アップし、次にメッセージ ボックス データベースを追加してスケール アウトします。  
  
> [!NOTE]
>  新しいメッセージ ボックス データベースの追加は、必ずしもサーバーの追加を意味しているわけではありません。 1 台の SQL Server に複数のメッセージ ボックス データベースを置くことができるためです。 また、データベースが複数のコンピューター上に存在すると、複数のメッセージ ボックス データベースにより DTC コストとネットワーク ホップが生じます。  
  
 マスター メッセージ ボックス データベースが飽和状態にならない限り、理論上は、SQL Server 層は無限にスケール アウトできます。  
  
 このセクションの各トピックでは、これらの拡張パターンについて詳しく説明します。 また、各パターンを拡張する方法とそのパターンでシステムを拡張できなくなった場合を判断する方法についても説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [スケーラビリティとは何ですか。](../core/what-is-scalability.md)  
  
-   [BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md)  
  
-   [BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md)  
  
-   [SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md)  
  
-   [SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md)  
  
## <a name="see-also"></a>参照  
 [スケール アウト受信ホスト](../core/scaled-out-receiving-hosts.md)   
 [スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md)   
 [スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md)   
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [スケール アウト データベース](../core/scaled-out-databases.md)   
 [BizTalk Server データベースをクラスタ リング](../core/clustering-the-biztalk-server-databases1.md)