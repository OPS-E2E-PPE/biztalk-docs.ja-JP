---
title: バックアップ セットの一部 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b9f15c0-4d31-4322-ac0a-8efdeed6f71e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baacc7a30a79084430ce570fc135b92e07586779
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291330"
---
# <a name="partial-backup-sets"></a><span data-ttu-id="822ee-102">バックアップ セットの一部</span><span class="sxs-lookup"><span data-stu-id="822ee-102">Partial Backup Sets</span></span>
<span data-ttu-id="822ee-103">ソース システム上のデータベースのバックアップ、問題がバックアップ セットの一部では、その結果発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="822ee-103">When backing up the databases on the source system, problems may occur that result in a partial backup set.</span></span> <span data-ttu-id="822ee-104">Master.dbo.bts_LogShippingHistory テーブルには、0 にが含まれますこれが発生したときに、 **SetComplete**セット内のすべてのレコードの列。</span><span class="sxs-lookup"><span data-stu-id="822ee-104">When this occurs, the Master.dbo.bts_LogShippingHistory table will contain a 0 in the **SetComplete** column for all records in the set.</span></span>  
  
 <span data-ttu-id="822ee-105">これらのセットを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="822ee-105">These sets cannot be restored.</span></span> <span data-ttu-id="822ee-106">その結果、ログのバックアップ セットのチェーンは解除されます。</span><span class="sxs-lookup"><span data-stu-id="822ee-106">As a result the log backup set chain is broken.</span></span> <span data-ttu-id="822ee-107">セットを無視する必要があります、すべてのログとバックアップ セットをその後、[次へ] の完全バックアップ セットへ。</span><span class="sxs-lookup"><span data-stu-id="822ee-107">The set must be ignored, as well as all log backup sets after it, up to the next full backup set.</span></span> <span data-ttu-id="822ee-108">[次へ] の有効な完全バックアップ セットの復元ジョブが自動的になります。</span><span class="sxs-lookup"><span data-stu-id="822ee-108">The restore job will automatically look for the next valid full backup set.</span></span> <span data-ttu-id="822ee-109">1 つ検出されません、失敗し、復元先の環境を修復するために設定されます。</span><span class="sxs-lookup"><span data-stu-id="822ee-109">If it does not find one, it fails and restores that set in order to repair the destination environment.</span></span>  
  
 <span data-ttu-id="822ee-110">ほとんどの場合、バックアップ セットの一部が発生し、次回実行するように構成されている場合、完全バックアップ セットが自動的に生成されますには、ソース システムを検出します。</span><span class="sxs-lookup"><span data-stu-id="822ee-110">In most cases the source system will detect that a partial backup set has occurred and will automatically produce a full backup set the next time it runs if it is configured to do so.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="822ee-111">この問題の最も一般的な原因は、送信先システムでファイル グループのディスク領域不足です。</span><span class="sxs-lookup"><span data-stu-id="822ee-111">The most common cause of this problem is insufficient disk space for the file groups on the destination system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="822ee-112">参照</span><span class="sxs-lookup"><span data-stu-id="822ee-112">See Also</span></span>  
 [<span data-ttu-id="822ee-113">ログ配布のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="822ee-113">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)