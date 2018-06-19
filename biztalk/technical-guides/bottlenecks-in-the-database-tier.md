---
title: データベース層のボトルネック |Microsoft ドキュメント
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
ms.openlocfilehash: b741f1ffcd68f7a5c739731e5aa9a1db55be34c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299946"
---
# <a name="bottlenecks-in-the-database-tier"></a><span data-ttu-id="500da-102">データベース層のボトルネック</span><span class="sxs-lookup"><span data-stu-id="500da-102">Bottlenecks in the Database Tier</span></span>
<span data-ttu-id="500da-103">このセクションでは、BizTalk メッセージ ボックス データベース、追跡データベース、および BAM プライマリ インポート データベースのボトルネックを特定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="500da-103">This section explains how to identify bottlenecks in the BizTalk MessageBox database, Tracking database, and BAM Primary Import database.</span></span> <span data-ttu-id="500da-104">ディスクの競合を回避する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="500da-104">It also explains how to avoid disk contention.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="500da-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="500da-105">In This Section</span></span>  
  
-   [<span data-ttu-id="500da-106">メッセージ ボックス データベース Database1 のボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="500da-106">How to Identify Bottlenecks in the MessageBox Database1</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)  
  
-   [<span data-ttu-id="500da-107">追跡データベースのボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="500da-107">How to Identify Bottlenecks in the Tracking Database</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-tracking-database.md)  
  
-   [<span data-ttu-id="500da-108">BAM プライマリ インポート データベースのボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="500da-108">How to Identify Bottlenecks in the BAM Primary Import Database</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-bam-primary-import-database.md)  
  
-   [<span data-ttu-id="500da-109">ディスク Contention2 を回避する方法</span><span class="sxs-lookup"><span data-stu-id="500da-109">How to Avoid Disk Contention2</span></span>](../technical-guides/how-to-avoid-disk-contention2.md)