---
title: "バックアップの BizTalk Server のジョブ内のデータベースを復元する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9bcac40f-ef0b-4ff0-8743-cf1614e14422
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb7c52b810343c1807e982e637372c74baeb84fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-restore-databases-in-the-backup-biztalk-server-job"></a>バックアップの BizTalk Server のジョブ内のデータベースを復元する方法
このセクションでは、BizTalk Server のバックアップ ジョブでバックアップされている BizTalk グループ内のデータベースをオンラインにする手順について説明します。 既定では、すべてのデータベースは、BAM データベースを除く BizTalk Server のバックアップ ジョブを使用してバックアップされます。 参照してください[Analysis Services の復元とデータベースのサポート](../technical-guides/restoring-analysis-services-and-supporting-databases.md)BAM データベースのバックアップと復元の詳細についてはします。 データベース間のトランザクション状態の一貫性を保証するには、すべてのデータベースを同じマークに復元する必要があります。 詳細については、次を参照してください。[マークされたトランザクション、完全バックアップ、およびログ バックアップ](http://go.microsoft.com/fwlink/?LinkId=151565)(http://go.microsoft.com/fwlink/?LinkId=151565)。  
  
 詳細情報および手順についてのデータベースの復元は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[、データベースを復元する方法](http://go.microsoft.com/fwlink/?LinkId=151406)(http://go.microsoft.com/fwlink/?LinkId=151406)。  
  
## <a name="see-also"></a>参照  
 [バックアップの BizTalk Server のジョブに含まれていないデータベースの復元](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)