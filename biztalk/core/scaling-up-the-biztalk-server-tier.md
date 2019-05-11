---
title: BizTalk Server 層のスケール アップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- scaling, scaling up
ms.assetid: 9002006a-f301-4e15-94b9-6caffd7c527c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6debecada3269374e2fd6f91a06d9e120c2538e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308808"
---
# <a name="scaling-up-the-biztalk-server-tier"></a>BizTalk Server 層のスケール アップ
BizTalk 層を拡大するには、CPU、メモリ、IO、およびその他のリソースをアップグレードします。 次の図は、次の 4 つのプロセッサのコンピューターに 2 つのプロセッサのコンピューターから、BizTalk 層をスケールとする方法の例を示します。  
  
 ![スケール&#45;を BTS](../core/media/scaleupbts.gif "ScaleUpBTS")  
  
 BizTalk 層のスケール アップのシナリオでは、スケール アウトを選択したときに似ています。  
  
-   BizTalk Server では、ボトルネックになります。 次の問題のいずれかでは、ボトルネックが考えられます。  
  
-   CPU:シナリオでは、CPU 負荷のかかるパイプライン、マップ、またはオーケストレーションを使用する場合、BizTalk server には余分な CPU ヘッドルームはありません。  
  
-   メモリと I/O:既存のコンピューター メモリ、IO、およびコンピューターの最大値に達した場合は、アップグレードする必要があります。  
  
-   スケール アウトは、コストが高すぎます。  
  
-   スケール アウトの場合は、ボトルネックを解消していません。 たとえば、スケール アウト扱いません次のボトルネック。  
  
    -   サイズの大きいメッセージの変換  
  
    -   インターチェンジごとのメッセージの数が多い  
  
    -   一部のパイプラインやアダプターなどの BTS コンポーネントで高いメモリ使用率  
  
    -   EDI などのトランスポート。  
  
## <a name="when-you-cant-scale-up-the-biztalk-tier"></a>ときに、BizTalk 層をスケールすることはできません。  
  
-   メッセージ ボックス データベースでは、ボトルネックです。  
  
-   アダプターがボトルネックになります。 たとえば、BizTalk の受信者数を増やした後、アダプターを使用する場合ロックの競合を BizTalk アダプターがデータを抽出するバックエンド アプリケーションで増やす可能性があります。 これは、アダプターのスケール アップする能力を制限します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md)   
 [SQL Server 層のスケール アップ](../core/scaling-up-the-sql-server-tier.md)   
 [SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md)   
 [受信ホスト スケール アウト](../core/scaled-out-receiving-hosts.md)   
 [スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md)   
 [スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md)   
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [スケール アウト データベース](../core/scaled-out-databases.md)   
 [BizTalk Server データベースのクラスタリング](../core/clustering-the-biztalk-server-databases1.md)