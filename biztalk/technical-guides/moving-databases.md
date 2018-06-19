---
title: データベースの移動 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a0d09a1-90a5-4a5d-a783-b979724e101b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5dd25f898890225300f8962e581a38912f36351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299034"
---
# <a name="moving-databases"></a>データベースの移動
移動するための推奨される方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を構成するのには、データベース (ビジネス アクティビティ監視 (BAM) データベース) を除く[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のセクションで説明したログ配布[災害復旧](../technical-guides/disaster-recovery.md)です。 すべての BAM で使用されるデータベースを除き、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用してデータベースをバックアップすることができます、 **Backup BizTalk Server** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。 このジョブの詳細については、次を参照してください。[を BizTalk Server のバックアップ ジョブをスケジュールする方法](http://go.microsoft.com/fwlink/?LinkId=154674)(http://go.microsoft.com/fwlink/?LinkId=154674) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
 このセクションでは、BAM に関連するデータベースを移動する方法と、残りを移動する方法について説明します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最初を構成しなくてもデータベース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布します。 アップグレードするときに、この方法が便利可能性があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納するコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースまたは災害復旧に関連していない他のシナリオでします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BAM データベースの移動](../technical-guides/moving-bam-databases.md)  
  
-   [非 BAM データベースの移動](../technical-guides/moving-non-bam-databases.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server2 の管理](../technical-guides/managing-biztalk-server2.md)