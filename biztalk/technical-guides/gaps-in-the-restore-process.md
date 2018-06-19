---
title: 復元プロセスのギャップ |Microsoft ドキュメント
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
ms.openlocfilehash: 2b7d3ccadd950f5a955430b982c1a6f79a262864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298098"
---
# <a name="gaps-in-the-restore-process"></a><span data-ttu-id="f2123-102">復元プロセスのギャップ</span><span class="sxs-lookup"><span data-stu-id="f2123-102">Gaps in the Restore Process</span></span>
<span data-ttu-id="f2123-103">Master.dbo.bts_LogShippingHistory テーブルのレコードを確認するには、復元されたセット内のギャップがわかります。</span><span class="sxs-lookup"><span data-stu-id="f2123-103">When reviewing records in the Master.dbo.bts_LogShippingHistory table, you may observe gaps in restored sets.</span></span> <span data-ttu-id="f2123-104">これにはいくつかの理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="f2123-104">This can occur for several reasons.</span></span> <span data-ttu-id="f2123-105">ただし、ギャップが発生した場合でも、送信先システムの安定性を復元することができます。</span><span class="sxs-lookup"><span data-stu-id="f2123-105">However, the stability of the destination system can be restored even when gaps have occurred.</span></span> <span data-ttu-id="f2123-106">ギャップの後に、送信先の環境を修復する設定の完全バックアップの復元を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2123-106">A gap must be followed by a restore of a full backup set to repair the destination environment.</span></span> <span data-ttu-id="f2123-107">ギャップが続いていない場合、完全バックアップの復元の設定、先の環境が安定しない一貫した状態に復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="f2123-107">If a gap is not followed by a full backup set restore, the destination environment is not stable and cannot be restored in a consistent state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2123-108">本来、完全バックアップを復元する目的は、データベースの初期状態を作成したり、ログ履歴バックアップ チェーンの問題を修復したりすることです。</span><span class="sxs-lookup"><span data-stu-id="f2123-108">Full backups are only restored to initially create the database and to repair problems in the log history backup chain.</span></span> <span data-ttu-id="f2123-109">復元で問題が発生しない限り、完全バックアップ セットは復元されません、ログ バックアップ チェーンに、参加していないためです。</span><span class="sxs-lookup"><span data-stu-id="f2123-109">As long as a problem does not occur with a restore, full backup sets are not restored, because they do not participate in the log backup chain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2123-110">参照</span><span class="sxs-lookup"><span data-stu-id="f2123-110">See Also</span></span>  
 [<span data-ttu-id="f2123-111">ログ配布のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f2123-111">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)