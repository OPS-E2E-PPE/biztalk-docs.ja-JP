---
title: バックアップ BizTalk Server のジョブ内のデータベースを復元する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9bcac40f-ef0b-4ff0-8743-cf1614e14422
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fde33b46937118aa29aa8259225da2c4d2c0439
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992411"
---
# <a name="how-to-restore-databases-in-the-backup-biztalk-server-job"></a>バックアップ BizTalk Server のジョブ内のデータベースを復元する方法
このセクションでは、BizTalk Server のバックアップ ジョブでバックアップされている BizTalk グループ内のデータベースをオンラインにする手順について説明します。 既定では、すべてのデータベースは、BAM データベースを除く、BizTalk Server のバックアップ ジョブを使用してバックアップされます。 参照してください[Analysis Services の復元とデータベースのサポート](../technical-guides/restoring-analysis-services-and-supporting-databases.md)BAM データベースのバックアップと復元の詳細についてはします。 データベース間のトランザクション状態の一貫性を保証するには、すべてのデータベースを同じマークに復元する必要があります。 詳細については、次を参照してください。[マークされたトランザクション、完全バックアップ、およびログ バックアップ](http://go.microsoft.com/fwlink/?LinkId=151565)(http://go.microsoft.com/fwlink/?LinkId=151565)します。  
  
 詳細と手順についてのデータベースの復元について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[、データベースを復元する方法](http://go.microsoft.com/fwlink/?LinkId=151406)(<http://go.microsoft.com/fwlink/?LinkId=151406>)。  
  
## <a name="see-also"></a>参照  
 [バックアップ BizTalk Server ジョブに含まれていないデータベースの復元](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)