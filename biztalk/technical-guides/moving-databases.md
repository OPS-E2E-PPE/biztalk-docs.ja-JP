---
title: データベースの移動 |Microsoft Docs
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
ms.openlocfilehash: 15562fc1fb642a4766190dabe912e81b38bb1ea8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972419"
---
# <a name="moving-databases"></a>データベースの移動
移動するための推奨される方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成することです (ビジネス アクティビティ監視 (BAM) データベース) を除くデータベース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]」セクションの説明に従って、ログ配布[ディザスター リカバリー](../technical-guides/disaster-recovery.md)します。 を除き、すべての BAM で使用されるデータベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用してデータベース バックアップすることができます、 **Backup BizTalk Server** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。 このジョブの詳細については、次を参照してください。 [Backup BizTalk Server のジョブをスケジュールする方法](http://go.microsoft.com/fwlink/?LinkId=154674)(<http://go.microsoft.com/fwlink/?LinkId=154674>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
 このセクションでは、BAM に関連するデータベースを移動する方法と、残りを移動する方法について説明します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最初を構成することなくデータベース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布します。 アップグレードするときに、この方法が便利な可能性があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納しているコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースまたはディザスター リカバリーには関連しない他のシナリオでします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BAM データベースの移動](../technical-guides/moving-bam-databases.md)  
  
-   [非 BAM データベースの移動](../technical-guides/moving-non-bam-databases.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server2 の管理](../technical-guides/managing-biztalk-server2.md)