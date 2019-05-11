---
title: 分散システムの問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 287b0adb-d5f9-4e47-80f8-0ba5d90c7864
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674af4da96fe62c4955ea93af5c2026f850dafe6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305712"
---
# <a name="distributed-system-problems"></a><span data-ttu-id="097a8-102">分散システムの問題</span><span class="sxs-lookup"><span data-stu-id="097a8-102">Distributed System Problems</span></span>
<span data-ttu-id="097a8-103">分散型の変換先のシステムで、復元ジョブの対象はエラーまたはその他のコンピューター上の問題の認識しません。</span><span class="sxs-lookup"><span data-stu-id="097a8-103">In a distributed destination system the restore jobs are not aware of errors or problems on the other computers.</span></span> <span data-ttu-id="097a8-104">たとえば、コンピューター A は、BizTalk 管理データベースと BizTalk 追跡データベースを復元して、コンピューター B が BizTalk メッセージ ボックス データベースを復元することです。</span><span class="sxs-lookup"><span data-stu-id="097a8-104">For example, suppose that computer A is restoring the BizTalk Management database and the BizTalk Tracking database, and computer B is restoring the BizTalk MessageBox database.</span></span> <span data-ttu-id="097a8-105">両方のコンピューターでは、1 ~ 25 のバックアップ セットが正常に復元します。</span><span class="sxs-lookup"><span data-stu-id="097a8-105">Both computers successfully restore backup sets 1 through 25.</span></span> <span data-ttu-id="097a8-106">ただし、セット、26 には、BizTalk メッセージ ボックス データベースの破損したログ バックアップ ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="097a8-106">Set 26, however, has a corrupted log backup file of the BizTalk MessageBox database.</span></span> <span data-ttu-id="097a8-107">コンピューター A は、そのデータベースを正しく復元しますが、破損したファイルを復元するコンピューター B が失敗します。</span><span class="sxs-lookup"><span data-stu-id="097a8-107">Computer A restores its databases correctly but computer B fails to restore the corrupted file.</span></span>  
  
 <span data-ttu-id="097a8-108">このような状況で、ソース システム上完全バックアップを強制します。</span><span class="sxs-lookup"><span data-stu-id="097a8-108">In this situation, force a full backup on the source system.</span></span> <span data-ttu-id="097a8-109">上記の例を続行するには、問題の診断を 35 のセットの完全バックアップが作成されたものとします。</span><span class="sxs-lookup"><span data-stu-id="097a8-109">Continuing the example above, assume that the problem was diagnosed and a full backup was created for set 35.</span></span> <span data-ttu-id="097a8-110">完全バックアップは 35 を設定し、それ以降のログのバックアップ セットの 36 (覚えて必要があるが常に一連の 1 つの後続の完全なログ バックアップが復元されるまでコンピューター B のコンピューター上の問題を認識してではないために、失敗復元セット 34 26、その後、コンピューター Ad)。</span><span class="sxs-lookup"><span data-stu-id="097a8-110">Computer A then restores sets 26 to 34, because it is not aware of the problem on Computer B. Computer B will fail until it sees full backup set 35 and subsequent log backup set 36 (remember that there must always be one subsequent complete log backup for a set to be restored).</span></span> <span data-ttu-id="097a8-111">35 から 36 のセットがコンピューター B に届いたら、その 35 を使用して自身を修復します。</span><span class="sxs-lookup"><span data-stu-id="097a8-111">When sets 35 and 36 arrive on computer B, it will repair itself using 35.</span></span> <span data-ttu-id="097a8-112">修復が完了したら、コンピューター A と B が同期されます。</span><span class="sxs-lookup"><span data-stu-id="097a8-112">After the repair is complete, computer A and B will be in sync.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="097a8-113">参照</span><span class="sxs-lookup"><span data-stu-id="097a8-113">See Also</span></span>  
 [<span data-ttu-id="097a8-114">ログ配布のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="097a8-114">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)