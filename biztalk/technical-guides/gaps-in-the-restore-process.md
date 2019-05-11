---
title: 復元プロセスのギャップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 616c4f36-8ed6-4b99-b97a-5635627dfc17
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06de30faec798fe57f30299051dc7f97db285bcf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279061"
---
# <a name="gaps-in-the-restore-process"></a><span data-ttu-id="14efc-102">復元プロセスのギャップ</span><span class="sxs-lookup"><span data-stu-id="14efc-102">Gaps in the Restore Process</span></span>
<span data-ttu-id="14efc-103">Master.dbo.bts_LogShippingHistory テーブルのレコードを確認する際に、復元されたセット内のギャップを確認できます。</span><span class="sxs-lookup"><span data-stu-id="14efc-103">When reviewing records in the Master.dbo.bts_LogShippingHistory table, you may observe gaps in restored sets.</span></span> <span data-ttu-id="14efc-104">これにはいくつかの理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="14efc-104">This can occur for several reasons.</span></span> <span data-ttu-id="14efc-105">ただし、ギャップが発生した場合でも、送信先システムの安定性を復元できます。</span><span class="sxs-lookup"><span data-stu-id="14efc-105">However, the stability of the destination system can be restored even when gaps have occurred.</span></span> <span data-ttu-id="14efc-106">ギャップの後に、送信先の環境を修復する設定の完全バックアップの復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14efc-106">A gap must be followed by a restore of a full backup set to repair the destination environment.</span></span> <span data-ttu-id="14efc-107">ギャップの後、完全バックアップの設定の復元、移行先の環境が安定しないと、一貫した状態で復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="14efc-107">If a gap is not followed by a full backup set restore, the destination environment is not stable and cannot be restored in a consistent state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14efc-108">本来、完全バックアップを復元する目的は、データベースの初期状態を作成したり、ログ履歴バックアップ チェーンの問題を修復したりすることです。</span><span class="sxs-lookup"><span data-stu-id="14efc-108">Full backups are only restored to initially create the database and to repair problems in the log history backup chain.</span></span> <span data-ttu-id="14efc-109">復元を使用した問題が発生しない限り、完全バックアップ セットは復元され、ログ バックアップ チェーンに、参加していないためです。</span><span class="sxs-lookup"><span data-stu-id="14efc-109">As long as a problem does not occur with a restore, full backup sets are not restored, because they do not participate in the log backup chain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14efc-110">参照</span><span class="sxs-lookup"><span data-stu-id="14efc-110">See Also</span></span>  
 [<span data-ttu-id="14efc-111">ログ配布のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="14efc-111">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)