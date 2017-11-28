---
title: "バックアップ セットの一部 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b9f15c0-4d31-4322-ac0a-8efdeed6f71e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9740cb0f45d6bb46c13a95e50e4717ef142b164
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="partial-backup-sets"></a><span data-ttu-id="a1a3b-102">バックアップ セットの一部</span><span class="sxs-lookup"><span data-stu-id="a1a3b-102">Partial Backup Sets</span></span>
<span data-ttu-id="a1a3b-103">ソース システム上のデータベースのバックアップ時にバックアップ セットの一部になる問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a1a3b-103">When backing up the databases on the source system, problems may occur that result in a partial backup set.</span></span> <span data-ttu-id="a1a3b-104">これが発生すると、Master.dbo.bts_LogShippingHistory テーブルが含まで 0、 **SetComplete**セット内のすべてのレコードの列です。</span><span class="sxs-lookup"><span data-stu-id="a1a3b-104">When this occurs, the Master.dbo.bts_LogShippingHistory table will contain a 0 in the **SetComplete** column for all records in the set.</span></span>  
  
 <span data-ttu-id="a1a3b-105">これらのセットを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="a1a3b-105">These sets cannot be restored.</span></span> <span data-ttu-id="a1a3b-106">その結果、ログのバックアップ セットのチェーンが壊れています。</span><span class="sxs-lookup"><span data-stu-id="a1a3b-106">As a result the log backup set chain is broken.</span></span> <span data-ttu-id="a1a3b-107">すべてのログとバックアップ セットをその後、次の完全バックアップ セットまで、セットを無視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1a3b-107">The set must be ignored, as well as all log backup sets after it, up to the next full backup set.</span></span> <span data-ttu-id="a1a3b-108">次の有効な完全バックアップ セットの復元ジョブが自動的になります。</span><span class="sxs-lookup"><span data-stu-id="a1a3b-108">The restore job will automatically look for the next valid full backup set.</span></span> <span data-ttu-id="a1a3b-109">実行していないため、失敗し、復元先の環境を修復するために設定されます。</span><span class="sxs-lookup"><span data-stu-id="a1a3b-109">If it does not find one, it fails and restores that set in order to repair the destination environment.</span></span>  
  
 <span data-ttu-id="a1a3b-110">ほとんどの場合、送信元システムことが検出バックアップ セットの一部が発生しましたし、次回実行するように構成されている場合、完全バックアップ セットが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="a1a3b-110">In most cases the source system will detect that a partial backup set has occurred and will automatically produce a full backup set the next time it runs if it is configured to do so.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1a3b-111">この問題の最も一般的な原因は、ターゲット システム上のファイル グループのディスク領域不足です。</span><span class="sxs-lookup"><span data-stu-id="a1a3b-111">The most common cause of this problem is insufficient disk space for the file groups on the destination system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a3b-112">参照</span><span class="sxs-lookup"><span data-stu-id="a1a3b-112">See Also</span></span>  
 [<span data-ttu-id="a1a3b-113">ログ配布のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a1a3b-113">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)