---
title: "BizTalk Server 層のスケール アップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- scaling, scaling up
ms.assetid: 9002006a-f301-4e15-94b9-6caffd7c527c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d55176072cd33e20dd1024bf2d9d1c39bca4567a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-up-the-biztalk-server-tier"></a>BizTalk Server 層のスケール アップ
BizTalk 層をスケール アップするには、CPU、メモリ、I/O、およびその他のリソースをアップグレードします。 次の図は、BizTalk 層を 2 台のプロセッサを搭載したコンピューターから 4 台のプロセッサを搭載したコンピューターにスケール アップする方法の例を示しています。  
  
 ![スケール &#45; 最大 BTS](../core/media/scaleupbts.gif "ScaleUpBTS")  
  
 BizTalk 層のスケール アップのシナリオは、スケール アウトを選択したときのシナリオに似ています。  
  
-   BizTalk Server がボトルネックになります。 ボトルネックは、次のいずれかの問題によって引き起こされる可能性があります。  
  
-   CPU: CPU を集中的に使用するパイプライン、マップ、またはオーケストレーションをシナリオで使用する場合に、BizTalk Server に余分な CPU ヘッドルームがない。  
  
-   メモリおよび I/O: 既存のコンピューターでメモリおよび I/O の最大値に達した場合は、コンピューターをアップグレードする必要があります。  
  
-   スケール アウトは、非常にコストがかかります。  
  
-   スケールアウトしてもボトルネックが改善されない場合があります。 たとえば、次のボトルネックはスケール アウトでは改善されません。  
  
    -   サイズの大きいメッセージを変換する。  
  
    -   1 回のインターチェンジに多数のメッセージを処理する。  
  
    -   パイプラインやアダプターなど、一部の BTS コンポーネントで多くのメモリを使用する。  
  
    -   EDI などのトランスポート。  
  
## <a name="when-you-cant-scale-up-the-biztalk-tier"></a>BizTalk 層をスケール アップできないケース  
  
-   メッセージ ボックス データベースがボトルネックの場合。  
  
-   アダプターがボトルネックになる場合。 たとえば、BizTalk の受信者数を増やした後、アダプターを使用している、ロックの競合が、BizTalk アダプターがデータを抽出するバックエンド アプリケーションで高まる可能性があります。 このため、アダプターのスケール アップが制限されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md)   
 [SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md)   
 [SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md)   
 [スケール アウト受信ホスト](../core/scaled-out-receiving-hosts.md)   
 [スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md)   
 [スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md)   
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [スケール アウト データベース](../core/scaled-out-databases.md)   
 [BizTalk Server データベースをクラスタ リング](../core/clustering-the-biztalk-server-databases1.md)