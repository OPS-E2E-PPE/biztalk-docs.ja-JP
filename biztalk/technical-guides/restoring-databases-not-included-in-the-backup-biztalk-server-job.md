---
title: バックアップ BizTalk Server のジョブに含まれていないデータベースの復元 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7141980-d4a6-4409-be9b-c94a7f733376
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e4555b9a3f635d733d698109614c1ed673125f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291259"
---
# <a name="restoring-databases-not-included-in-the-backup-biztalk-server-job"></a><span data-ttu-id="e6b0a-102">バックアップ BizTalk Server のジョブに含まれていないデータベースの復元</span><span class="sxs-lookup"><span data-stu-id="e6b0a-102">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>
<span data-ttu-id="e6b0a-103">このセクションでは、BizTalk Server のバックアップ ジョブによってバックアップされませんは全体的な BizTalk ソリューションの一部のデータベースを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6b0a-103">This section describes how to restore databases that are part of the overall BizTalk solution but are not backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="e6b0a-104">BizTalk ソリューションの一部であるすべてのデータベースは、次を除く、BizTalk Server のバックアップ ジョブを使用してバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="e6b0a-104">All databases that are part of a BizTalk solution will be backed up by using the Backup BizTalk Server job except for the following:</span></span>  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] <span data-ttu-id="e6b0a-105">Analysis Services データベース</span><span class="sxs-lookup"><span data-stu-id="e6b0a-105">Analysis Services databases</span></span>  
  
- <span data-ttu-id="e6b0a-106">BAM が有効になっているが、BM.exe を使用して構成されている場合、BAM データベース</span><span class="sxs-lookup"><span data-stu-id="e6b0a-106">BAM databases when BAM is enabled and configured using BM.exe</span></span>  
  
  <span data-ttu-id="e6b0a-107">このセクションも上に挙げたデータベースの復元後のデータベース参照を更新する方法について説明し、不完全な BAM アクティビティ インスタンスの解決に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6b0a-107">This section also describes how to update database references after restoring the databases listed above and includes information about resolving incomplete BAM activity instances.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e6b0a-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e6b0a-108">In This Section</span></span>  
  
-   [<span data-ttu-id="e6b0a-109">Analysis Services とサポートするデータベースの復元</span><span class="sxs-lookup"><span data-stu-id="e6b0a-109">Restoring Analysis Services and Supporting Databases</span></span>](../technical-guides/restoring-analysis-services-and-supporting-databases.md)  
  
-   [<span data-ttu-id="e6b0a-110">データベース参照の更新</span><span class="sxs-lookup"><span data-stu-id="e6b0a-110">Updating Database References</span></span>](../technical-guides/updating-database-references.md)  
  
-   [<span data-ttu-id="e6b0a-111">不完全な BAM アクティビティ インスタンスを解決する方法</span><span class="sxs-lookup"><span data-stu-id="e6b0a-111">How to Resolve Incomplete BAM Activity Instances</span></span>](../technical-guides/how-to-resolve-incomplete-bam-activity-instances.md)