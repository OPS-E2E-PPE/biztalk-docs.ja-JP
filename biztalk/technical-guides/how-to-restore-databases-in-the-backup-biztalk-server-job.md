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
# <a name="how-to-restore-databases-in-the-backup-biztalk-server-job"></a><span data-ttu-id="eca31-102">バックアップ BizTalk Server のジョブ内のデータベースを復元する方法</span><span class="sxs-lookup"><span data-stu-id="eca31-102">How to Restore Databases in the Backup BizTalk Server Job</span></span>
<span data-ttu-id="eca31-103">このセクションでは、BizTalk Server のバックアップ ジョブでバックアップされている BizTalk グループ内のデータベースをオンラインにする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="eca31-103">This section covers the steps to bring online the databases in the BizTalk group that are backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="eca31-104">既定では、すべてのデータベースは、BAM データベースを除く、BizTalk Server のバックアップ ジョブを使用してバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="eca31-104">By default, all databases are backed up by using the Backup BizTalk Server job except for the BAM databases.</span></span> <span data-ttu-id="eca31-105">参照してください[Analysis Services の復元とデータベースのサポート](../technical-guides/restoring-analysis-services-and-supporting-databases.md)BAM データベースのバックアップと復元の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="eca31-105">See [Restoring Analysis Services and Supporting Databases](../technical-guides/restoring-analysis-services-and-supporting-databases.md) for more information about backup and restore of the BAM databases.</span></span> <span data-ttu-id="eca31-106">データベース間のトランザクション状態の一貫性を保証するには、すべてのデータベースを同じマークに復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eca31-106">You must restore all databases to the same mark to ensure a consistent transactional state among the databases.</span></span> <span data-ttu-id="eca31-107">詳細については、[マークされたトランザクション、完全バックアップ、およびログ バックアップ](http://go.microsoft.com/fwlink/?LinkId=151565)(http://go.microsoft.com/fwlink/?LinkId=151565)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eca31-107">For more information, see [Marked Transactions, Full Backups, and Log Backups](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565).</span></span>  
  
 <span data-ttu-id="eca31-108">詳細と手順についてのデータベースの復元について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[、データベースを復元する方法](http://go.microsoft.com/fwlink/?LinkId=151406)(<http://go.microsoft.com/fwlink/?LinkId=151406>)。</span><span class="sxs-lookup"><span data-stu-id="eca31-108">For more information and instructions about restoring databases for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [How to Restore Your Databases](http://go.microsoft.com/fwlink/?LinkId=151406) (<http://go.microsoft.com/fwlink/?LinkId=151406>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca31-109">参照</span><span class="sxs-lookup"><span data-stu-id="eca31-109">See Also</span></span>  
 [<span data-ttu-id="eca31-110">バックアップ BizTalk Server ジョブに含まれていないデータベースの復元</span><span class="sxs-lookup"><span data-stu-id="eca31-110">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)