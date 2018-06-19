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
# <a name="moving-databases"></a><span data-ttu-id="b5d4b-102">データベースの移動</span><span class="sxs-lookup"><span data-stu-id="b5d4b-102">Moving Databases</span></span>
<span data-ttu-id="b5d4b-103">移動するための推奨される方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を構成するのには、データベース (ビジネス アクティビティ監視 (BAM) データベース) を除く[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のセクションで説明したログ配布[災害復旧](../technical-guides/disaster-recovery.md)です。</span><span class="sxs-lookup"><span data-stu-id="b5d4b-103">The recommended method for moving [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases (except for the Business Activity Monitoring (BAM) databases) is to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping as described in the section [Disaster Recovery](../technical-guides/disaster-recovery.md).</span></span> <span data-ttu-id="b5d4b-104">すべての BAM で使用されるデータベースを除き、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用してデータベースをバックアップすることができます、 **Backup BizTalk Server** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。</span><span class="sxs-lookup"><span data-stu-id="b5d4b-104">With the exception of the databases used by BAM, all of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases can be backed up by using the **Backup BizTalk Server**[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent job.</span></span> <span data-ttu-id="b5d4b-105">このジョブの詳細については、次を参照してください。[を BizTalk Server のバックアップ ジョブをスケジュールする方法](http://go.microsoft.com/fwlink/?LinkId=154674)(http://go.microsoft.com/fwlink/?LinkId=154674) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="b5d4b-105">For more information about this job, see [How to Schedule the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkId=154674) (http://go.microsoft.com/fwlink/?LinkId=154674) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="b5d4b-106">このセクションでは、BAM に関連するデータベースを移動する方法と、残りを移動する方法について説明します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最初を構成しなくてもデータベース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布します。</span><span class="sxs-lookup"><span data-stu-id="b5d4b-106">This section describes how to move the BAM-related databases and how to move the remaining [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases without first configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping.</span></span> <span data-ttu-id="b5d4b-107">アップグレードするときに、この方法が便利可能性があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納するコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースまたは災害復旧に関連していない他のシナリオでします。</span><span class="sxs-lookup"><span data-stu-id="b5d4b-107">This approach may be useful when upgrading the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computers that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases or in other scenarios that are not related to disaster recovery.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5d4b-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b5d4b-108">In This Section</span></span>  
  
-   [<span data-ttu-id="b5d4b-109">BAM データベースの移動</span><span class="sxs-lookup"><span data-stu-id="b5d4b-109">Moving BAM Databases</span></span>](../technical-guides/moving-bam-databases.md)  
  
-   [<span data-ttu-id="b5d4b-110">非 BAM データベースの移動</span><span class="sxs-lookup"><span data-stu-id="b5d4b-110">Moving Non-BAM Databases</span></span>](../technical-guides/moving-non-bam-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="b5d4b-111">参照</span><span class="sxs-lookup"><span data-stu-id="b5d4b-111">See Also</span></span>  
 [<span data-ttu-id="b5d4b-112">BizTalk Server2 の管理</span><span class="sxs-lookup"><span data-stu-id="b5d4b-112">Managing BizTalk Server2</span></span>](../technical-guides/managing-biztalk-server2.md)