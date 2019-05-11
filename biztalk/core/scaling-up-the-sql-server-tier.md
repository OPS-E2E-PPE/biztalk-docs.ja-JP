---
title: SQL Server 層のスケール アップ |Microsoft Docs
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
- SQL Server, scaling
- scaling, scaling up
- scaling, strategies
ms.assetid: 4352c4af-6861-43d9-b433-9ca25668b439
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7642b09a9380dd33231fce7be85caee19e31a5fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308704"
---
# <a name="scaling-up-the-sql-server-tier"></a>SQL Server 層のスケール アップ
このパターンでは、既存の SQL メッセージ ボックス データベースのアップグレードにスループットや待機時間の要件に応じてスケールします。  
  
 次の図は、8 プロセッサ サーバーにクアッド プロセッサ サーバーからマスター メッセージ ボックス データベースがアップグレードされた、シナリオを示しています。  
  
 ![スケール&#45;を MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")  
  
## <a name="when-to-scale-up-the-sql-tier"></a>SQL 層をスケール アップするタイミング  
  
-   ときに、マスター メッセージ ボックス データベースをスケール アップすることができます。  
  
-   マスター メッセージ ボックス データベースがボトルネックになる場合。 ボトルネックが考えられます。  
  
    -   **CPU** 、非常に高価で複雑なオーケストレーション シナリオが発生した場合、メッセージ ボックスは大量の CPU リソースを消費します。 スケール アップ SQL server 個以上の Cpu を追加することでは、シナリオをスケールする必要があります。  
  
    -   **メモリまたは I/O**メモリまたは I/O のボトルネックになることができ、アップグレードすることができます。  
  
-   スケール アップ、スケール アウトよりも低コストとスケール アップは、ボトルネックに対処できます。 たとえば、マスター メッセージ ボックス データベースに SQL ロックの競合の問題がある場合は、スケール アップでこの問題は解決できません。  
  
## <a name="when-do-you-decide-sql-cannot-scale-up"></a>SQL をスケール アップできないと判断するでしょうか。  
 スケール アップは、SQL 層でのロック競合のボトルネックに対処ことはできません。 この種のボトルネックをヒットすると場合、スケール アウトは、スケール アップよりも優れたオプションです。  
  
## <a name="strategies-and-considerations-for-scaling-up-the-sql-tier"></a>戦略と SQL 層のスケール アップに関する考慮事項  
  
-   マスター メッセージ ボックス データベースを最初にスケール アップし、スケール アウトします。  
  
-   マスター メッセージ ボックス データベースがボトルネックとなる最終的になります。 高速で大容量マスター メッセージ ボックス データベースがそのため、する必要があります (たとえば、Itanium ベースの 64 ビットまたは x64 ベース、デュアル コア コンピューターなど)。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md)   
 [BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md)   
 [SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md)   
 [受信ホスト スケール アウト](../core/scaled-out-receiving-hosts.md)   
 [スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md)   
 [スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md)   
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [スケール アウト データベース](../core/scaled-out-databases.md)   
 [BizTalk Server データベースのクラスタリング](../core/clustering-the-biztalk-server-databases1.md)