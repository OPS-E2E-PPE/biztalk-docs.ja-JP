---
title: SQL Server 層のスケール アップ |Microsoft ドキュメント
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
ms.openlocfilehash: 6c654c4a3b1bba166ae8a49918f6ef31827cf041
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269682"
---
# <a name="scaling-up-the-sql-server-tier"></a>SQL Server 層のスケール アップ
このパターンで、スループットまたは待機時間の要件に応じて、既存の SQL メッセージ ボックス データベースをアップグレードしてスケール アップします。  
  
 次の図は、マスターのメッセージ ボックス データベースをクワド (4) プロセッサ サーバーから 8 プロセッサ サーバーにアップグレードするシナリオを示しています。  
  
 ![スケール &#45; 最大 MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")  
  
## <a name="when-to-scale-up-the-sql-tier"></a>SQL 層をスケール アップするタイミング  
  
-   マスターのメッセージ ボックス データベースをスケール アップするとき。  
  
-   マスターのメッセージ ボックス データベースがボトルネックになっている場合。 次のボトルネックが考えられます。  
  
    -   **CPU**非常に複雑なオーケストレーション シナリオが発生した場合、メッセージ ボックスは大量の CPU リソースを消費します。 CPU を追加して SQL Server をスケール アップすると、シナリオもスケール アップされます。  
  
    -   **メモリまたは I/O**メモリまたは I/O のボトルネックになることができ、アップグレードすることができます。  
  
-   スケール アップがスケール アウトよりもコストがかからず、スケール アップによりボトルネックを解消できる場合。 たとえば、マスターのメッセージ ボックス データベースに SQL のロックの競合があった場合、スケール アップではこの問題を解決できません。  
  
## <a name="when-do-you-decide-sql-cannot-scale-up"></a>SQL をスケール アップできないと判断するタイミング  
 スケール アップは、SQL 層のロックの競合のボトルネックを解消できません。 これらのボトルネックに達すると、スケール アウトがスケール アップよりも優れた手法です。  
  
## <a name="strategies-and-considerations-for-scaling-up-the-sql-tier"></a>SQL 層をスケール アップする方法と注意事項  
  
-   マスターのメッセージ ボックス データベースをスケール アップしてから、スケール アウトします。  
  
-   マスターのメッセージ ボックス データベースは、いずれはボトルネックとなります。 そのため、マスターのメッセージ ボックス データベースを高速で大容量にする必要があります (たとえば、Itanium ベースの 64 ビットまたは x64 ベースの、デュアル コア コンピューターなど)。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層のスケール アウト](../core/scaling-out-the-biztalk-server-tier.md)   
 [BizTalk Server 層のスケール アップ](../core/scaling-up-the-biztalk-server-tier.md)   
 [SQL Server 層のスケール アウト](../core/scaling-out-the-sql-server-tier.md)   
 [スケール アウト受信ホスト](../core/scaled-out-receiving-hosts.md)   
 [スケール アウトされた処理ホスト](../core/scaled-out-processing-hosts.md)   
 [スケール アウトされた送信ホスト](../core/scaled-out-sending-hosts.md)   
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [スケール アウト データベース](../core/scaled-out-databases.md)   
 [BizTalk Server データベースをクラスタ リング](../core/clustering-the-biztalk-server-databases1.md)