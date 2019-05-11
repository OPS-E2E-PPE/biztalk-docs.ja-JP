---
title: データベース層のボトルネック |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55b37393-32dc-4717-bf62-48588c23dd78
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65f8dbf3a1d1360bc552344eb989fccf239fc6f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400439"
---
# <a name="bottlenecks-in-the-database-tier"></a><span data-ttu-id="19ddf-102">データベース層のボトルネック</span><span class="sxs-lookup"><span data-stu-id="19ddf-102">Bottlenecks in the Database Tier</span></span>
<span data-ttu-id="19ddf-103">このセクションでは、BizTalk メッセージ ボックス データベース、追跡データベース、および BAM プライマリ インポート データベースのボトルネックを特定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="19ddf-103">This section explains how to identify bottlenecks in the BizTalk MessageBox database, Tracking database, and BAM Primary Import database.</span></span> <span data-ttu-id="19ddf-104">ディスクの競合を回避する方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="19ddf-104">It also explains how to avoid disk contention.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19ddf-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="19ddf-105">In This Section</span></span>  
  
-   [<span data-ttu-id="19ddf-106">メッセージ ボックス データベース 1 のボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="19ddf-106">How to Identify Bottlenecks in the MessageBox Database1</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)  
  
-   [<span data-ttu-id="19ddf-107">追跡データベースのボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="19ddf-107">How to Identify Bottlenecks in the Tracking Database</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-tracking-database.md)  
  
-   [<span data-ttu-id="19ddf-108">BAM プライマリ インポート データベースのボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="19ddf-108">How to Identify Bottlenecks in the BAM Primary Import Database</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-bam-primary-import-database.md)  
  
-   [<span data-ttu-id="19ddf-109">ディスク Contention2 を回避する方法</span><span class="sxs-lookup"><span data-stu-id="19ddf-109">How to Avoid Disk Contention2</span></span>](../technical-guides/how-to-avoid-disk-contention2.md)