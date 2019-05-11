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
ms.openlocfilehash: ce521277ee64819d6201ab24ced3066d2b3b10ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65278965"
---
# <a name="moving-databases"></a><span data-ttu-id="36cf4-102">データベースの移動</span><span class="sxs-lookup"><span data-stu-id="36cf4-102">Moving Databases</span></span>
<span data-ttu-id="36cf4-103">移動するための推奨される方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成することです (ビジネス アクティビティ監視 (BAM) データベース) を除くデータベース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]」セクションの説明に従って、ログ配布[ディザスター リカバリー](../technical-guides/disaster-recovery.md)します。</span><span class="sxs-lookup"><span data-stu-id="36cf4-103">The recommended method for moving [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases (except for the Business Activity Monitoring (BAM) databases) is to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping as described in the section [Disaster Recovery](../technical-guides/disaster-recovery.md).</span></span> <span data-ttu-id="36cf4-104">を除き、すべての BAM で使用されるデータベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用してデータベース バックアップすることができます、 **Backup BizTalk Server** [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブ。</span><span class="sxs-lookup"><span data-stu-id="36cf4-104">With the exception of the databases used by BAM, all of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases can be backed up by using the **Backup BizTalk Server**[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent job.</span></span> <span data-ttu-id="36cf4-105">このジョブの詳細については、次を参照してください。 [Backup BizTalk Server のジョブをスケジュールする方法](http://go.microsoft.com/fwlink/?LinkId=154674)(<http://go.microsoft.com/fwlink/?LinkId=154674>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="36cf4-105">For more information about this job, see [How to Schedule the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkId=154674) (<http://go.microsoft.com/fwlink/?LinkId=154674>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="36cf4-106">このセクションでは、BAM に関連するデータベースを移動する方法と、残りを移動する方法について説明します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最初を構成することなくデータベース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布します。</span><span class="sxs-lookup"><span data-stu-id="36cf4-106">This section describes how to move the BAM-related databases and how to move the remaining [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases without first configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping.</span></span> <span data-ttu-id="36cf4-107">アップグレードするときに、この方法が便利な可能性があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納しているコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースまたはディザスター リカバリーには関連しない他のシナリオでします。</span><span class="sxs-lookup"><span data-stu-id="36cf4-107">This approach may be useful when upgrading the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computers that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases or in other scenarios that are not related to disaster recovery.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36cf4-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="36cf4-108">In This Section</span></span>  
  
-   [<span data-ttu-id="36cf4-109">BAM データベースの移動</span><span class="sxs-lookup"><span data-stu-id="36cf4-109">Moving BAM Databases</span></span>](../technical-guides/moving-bam-databases.md)  
  
-   [<span data-ttu-id="36cf4-110">非 BAM データベースの移動</span><span class="sxs-lookup"><span data-stu-id="36cf4-110">Moving Non-BAM Databases</span></span>](../technical-guides/moving-non-bam-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="36cf4-111">参照</span><span class="sxs-lookup"><span data-stu-id="36cf4-111">See Also</span></span>  
 [<span data-ttu-id="36cf4-112">BizTalk Server2 の管理</span><span class="sxs-lookup"><span data-stu-id="36cf4-112">Managing BizTalk Server2</span></span>](../technical-guides/managing-biztalk-server2.md)