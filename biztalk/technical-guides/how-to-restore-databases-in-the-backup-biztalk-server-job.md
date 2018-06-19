---
title: バックアップの BizTalk Server のジョブ内のデータベースを復元する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: eb7c52b810343c1807e982e637372c74baeb84fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298562"
---
# <a name="how-to-restore-databases-in-the-backup-biztalk-server-job"></a><span data-ttu-id="e55d9-102">バックアップの BizTalk Server のジョブ内のデータベースを復元する方法</span><span class="sxs-lookup"><span data-stu-id="e55d9-102">How to Restore Databases in the Backup BizTalk Server Job</span></span>
<span data-ttu-id="e55d9-103">このセクションでは、BizTalk Server のバックアップ ジョブでバックアップされている BizTalk グループ内のデータベースをオンラインにする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e55d9-103">This section covers the steps to bring online the databases in the BizTalk group that are backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="e55d9-104">既定では、すべてのデータベースは、BAM データベースを除く BizTalk Server のバックアップ ジョブを使用してバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="e55d9-104">By default, all databases are backed up by using the Backup BizTalk Server job except for the BAM databases.</span></span> <span data-ttu-id="e55d9-105">参照してください[Analysis Services の復元とデータベースのサポート](../technical-guides/restoring-analysis-services-and-supporting-databases.md)BAM データベースのバックアップと復元の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="e55d9-105">See [Restoring Analysis Services and Supporting Databases](../technical-guides/restoring-analysis-services-and-supporting-databases.md) for more information about backup and restore of the BAM databases.</span></span> <span data-ttu-id="e55d9-106">データベース間のトランザクション状態の一貫性を保証するには、すべてのデータベースを同じマークに復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e55d9-106">You must restore all databases to the same mark to ensure a consistent transactional state among the databases.</span></span> <span data-ttu-id="e55d9-107">詳細については、次を参照してください。[マークされたトランザクション、完全バックアップ、およびログ バックアップ](http://go.microsoft.com/fwlink/?LinkId=151565)(http://go.microsoft.com/fwlink/?LinkId=151565)。</span><span class="sxs-lookup"><span data-stu-id="e55d9-107">For more information, see [Marked Transactions, Full Backups, and Log Backups](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565).</span></span>  
  
 <span data-ttu-id="e55d9-108">詳細情報および手順についてのデータベースの復元は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[、データベースを復元する方法](http://go.microsoft.com/fwlink/?LinkId=151406)(http://go.microsoft.com/fwlink/?LinkId=151406)。</span><span class="sxs-lookup"><span data-stu-id="e55d9-108">For more information and instructions about restoring databases for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [How to Restore Your Databases](http://go.microsoft.com/fwlink/?LinkId=151406) (http://go.microsoft.com/fwlink/?LinkId=151406).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e55d9-109">参照</span><span class="sxs-lookup"><span data-stu-id="e55d9-109">See Also</span></span>  
 [<span data-ttu-id="e55d9-110">バックアップの BizTalk Server のジョブに含まれていないデータベースの復元</span><span class="sxs-lookup"><span data-stu-id="e55d9-110">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)