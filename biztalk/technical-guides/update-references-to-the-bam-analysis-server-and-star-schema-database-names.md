---
title: BAM Analysis Server およびスター スキーマ データベース名への参照の更新 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 319caa26-1292-4453-a316-efca4fbffdb6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6052da82dd121d25f4cb160521d7c31f646a2305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400593"
---
# <a name="update-references-to-the-bam-analysis-server-and-star-schema-database-names"></a><span data-ttu-id="e921b-102">BAM Analysis Server およびスター スキーマ データベース名への参照の更新</span><span class="sxs-lookup"><span data-stu-id="e921b-102">Update References to the BAM Analysis Server and Star Schema Database Names</span></span>
<span data-ttu-id="e921b-103">BAM 分析データベースをバックアップした場合、システムまたはデータに障害が発生した場合、別のコンピューターにそのバックアップを復元することができ、バックアップの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e921b-103">If you backed up your BAM Analysis database, in the event of a system or data failure you can restore that backup to a different computer and you can rename the backup.</span></span>  
  
 <span data-ttu-id="e921b-104">BAM 分析およびスター スキーマ データベースを復元する手順を実行[Backup BizTalk Server ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)します。</span><span class="sxs-lookup"><span data-stu-id="e921b-104">To restore the BAM Analysis and Star Schema databases, perform the steps in [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span></span> <span data-ttu-id="e921b-105">さらに、BAM を更新する必要があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Integration Services (SSIS) パッケージを新しいサーバー名およびデータベース名。</span><span class="sxs-lookup"><span data-stu-id="e921b-105">In addition, you must update the BAM [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Integration Services (SSIS) packages with the new server name and database name.</span></span>  
  
## <a name="how-to-update-references-to-bam-analysis-server-and-star-schema-database-names"></a><span data-ttu-id="e921b-106">BAM Analysis Server およびスター スキーマ データベース名への参照を更新する方法</span><span class="sxs-lookup"><span data-stu-id="e921b-106">How to Update References to BAM Analysis Server and Star Schema Database Names</span></span>  
 <span data-ttu-id="e921b-107">BAM Analysis server データベースへの参照を更新する方法については、次を参照してください。[新しい BAM 分析データベースへの参照の更新](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)します。</span><span class="sxs-lookup"><span data-stu-id="e921b-107">For instructions on how to update references to BAM Analysis server databases, see [Updating References to the New BAM Analysis Database](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate).</span></span> <span data-ttu-id="e921b-108">BAM スター スキーマ データベースへの参照を更新する方法については、次を参照してください。[新しい BAM スター スキーマ データベースへの参照の更新](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)します。</span><span class="sxs-lookup"><span data-stu-id="e921b-108">For instructions on how to update references to the BAM Star Schema databases, see [Updating References to the New BAM Star Schema Database](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate).</span></span>