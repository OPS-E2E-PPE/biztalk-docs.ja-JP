---
title: BizTalk Server データベースの移動 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, databases
- BizTalk Server, maintaining
- BizTalk Server, migrating databases
- maintaining, BizTalk Server
- databases, migrating
ms.assetid: 445161b2-245a-4f75-8d54-59e1e81c0398
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb2effe8f274ab2d4f564a431d2c068fd8c55bcb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263170"
---
# <a name="moving-biztalk-server-databases"></a><span data-ttu-id="1f3d5-102">BizTalk Server データベースの移動</span><span class="sxs-lookup"><span data-stu-id="1f3d5-102">Moving BizTalk Server Databases</span></span>
<span data-ttu-id="1f3d5-103">さまざまなニーズに積極的に対応するデータ センターにおいて、データベースを別のハードウェアに移動することは決して珍しいことではありません。</span><span class="sxs-lookup"><span data-stu-id="1f3d5-103">In any active data center, databases sometimes need to be moved to different hardware.</span></span> <span data-ttu-id="1f3d5-104">データベースの移動が必要となるケースとしては、データベースがハードウェアの容量を超えてしまったり、ハードウェアを新しいハードウェアにアップグレードしたりする場合などが考えられます。</span><span class="sxs-lookup"><span data-stu-id="1f3d5-104">For example, you might need to move a database when the database outgrows its hardware or when the hardware is upgraded or replaced by newer equipment.</span></span> <span data-ttu-id="1f3d5-105">ここでは、いくつかの BizTalk Server データベースを対象に、その移動方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="1f3d5-105">The procedures in this section describe how to move the most commonly moved BizTalk Server databases.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f3d5-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1f3d5-106">In This Section</span></span>  
  
-   [<span data-ttu-id="1f3d5-107">BizTalk Server データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="1f3d5-107">How to Move the BizTalk Server Databases</span></span>](../core/how-to-move-the-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="1f3d5-108">BAM プライマリ インポート データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="1f3d5-108">How to Move the BAM Primary Import Database</span></span>](../core/how-to-move-the-bam-primary-import-database1.md)  
  
-   [<span data-ttu-id="1f3d5-109">BAM アーカイブ データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="1f3d5-109">How to Move the BAM Archive Database</span></span>](../core/how-to-move-the-bam-archive-database2.md)  
  
-   [<span data-ttu-id="1f3d5-110">BAM スター スキーマ データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="1f3d5-110">How to Move the BAM Star Schema Database</span></span>](../core/how-to-move-the-bam-star-schema-database1.md)  
  
-   [<span data-ttu-id="1f3d5-111">BAM 分析データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="1f3d5-111">How to Move the BAM Analysis Database</span></span>](../core/how-to-move-the-bam-analysis-database2.md)  
  
-   [<span data-ttu-id="1f3d5-112">Services データベースに BAM Notification を移動する方法</span><span class="sxs-lookup"><span data-stu-id="1f3d5-112">How to Move the BAM Notification Services Databases</span></span>](../core/how-to-move-the-bam-notification-services-databases2.md)